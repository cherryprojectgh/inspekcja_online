# Plan techniczny MVP — Inspekcja online

16 listopada 2026 · Zakres i kryteria odbioru określa [specyfikacja MVP](specyfikacja.md).

## Harmonogram

| Tydzień | Czas | Zadania | Wynik |
| --- | --- | --- | --- |
| 1 | 8–9 h | F00 (4 h), F01 (4 h), do 1 h rezerwy | Próba aparatu przez HTTPS na iPhonie i Samsungu, działający link do fikcyjnej sprawy i zapis akceptacji. |
| 2 | 8–9 h | F02 (3 h), F03 (5–6 h) | Zdjęcia z aparatu bez galerii, potwierdzony zapis, wznowienie od 3/8 i podmiana jednego ujęcia. |
| 3 | 8–9 h | F04 (3 h), odbiór i poprawki (5–6 h) | Zakończenie sprawy, potwierdzenie, weryfikacja granic dostępu i pełny odbiór na obu telefonach. |

Szacunek 24–27 godzin zakłada pięć godzinnych wieczorów i 3–4 godziny łącznie w każdy weekend. Jeśli próba aparatu nie przejdzie, najpierw ustal przyczynę na konkretnym urządzeniu. Nie zastępuj aparatu wyborem pliku. W razie opóźnienia ogranicz dopracowywanie wyglądu, zachowując instrukcje, dostępność przycisku i obowiązkowe kryteria.

## Aplikacja i środowisko

- Lekki frontend w TypeScript, HTML i CSS oraz jeden Cloudflare Worker obsługujący pliki interfejsu i żądania do API pod tym samym adresem. Ekrany i style oprzeć na [prototypie](../prototyp.html) oraz [DESIGN.md](../DESIGN.md). Prototyp używa pola wyboru pliku z atrybutem `capture`; w aplikacji zastąpi je podgląd z aparatu. Dla nowego projektu przyjąć Cloudflare CLI `cf`. [Workers Static Assets](https://developers.cloudflare.com/workers/static-assets/) · [Cloudflare CLI](https://developers.cloudflare.com/cf/agents/)
- PostgreSQL w odrębnym projekcie Supabase w regionie UE, preferencyjnie Frankfurt. Worker łączy się przez Hyperdrive z wyłączonym cache zapytań, żeby decyzje o dostępie i stanie sprawy opierały się na bieżących danych. Używać osobnej roli aplikacyjnej z uprawnieniami ograniczonymi do operacji MVP, bez DDL. Migracje i dane startowe uruchamiać osobnym dostępem administracyjnym w środowisku testowym. [Połączenie Hyperdrive z Supabase](https://developers.cloudflare.com/hyperdrive/examples/connect-to-postgres/postgres-database-providers/supabase/) · [Regiony Supabase](https://supabase.com/docs/guides/platform/regions)
- Zdjęcia trzymać w prywatnym Supabase Storage. Worker czyta i zapisuje je po uwierzytelnieniu linku. Klient otrzymuje obraz przez API Workera z `Cache-Control: no-store`. Dane sprawy także są zwracane z `no-store`. Klient nie dostaje adresu magazynu ani jego poświadczeń. Obsługa PostgreSQL i magazynu plików jest osobna, aby później można było wymienić dostawcę każdego z nich. [Prywatne zasobniki Supabase](https://supabase.com/docs/guides/storage/buckets/fundamentals)
- Zacząć od planów Free dla testu. Dokumentacja Workers podaje 100 tys. żądań dziennie i 10 ms czasu CPU na żądanie na planie Free. Supabase Free obejmuje 1 GB miejsca na pliki, a projekt może zostać wstrzymany przy niskiej aktywności przez siedem dni. Przy proponowanym limicie 4 MiB na zdjęcie jedna sprawa zajmie do 32 MiB aktywnych plików. Przed sesją sprawdzić dostępność projektu, a w pomiarze Workera uwzględnić zapis i odczyt największego zdjęcia. [Limity Workers](https://developers.cloudflare.com/workers/platform/limits/) · [Plany Supabase](https://supabase.com/pricing) · [Wstrzymywanie projektów](https://supabase.com/docs/guides/platform/free-project-pausing)

## F00 — fundament i szybka próba aparatu

1. Wystawić przez HTTPS sam ekran próby na odrębnym testowym Workerze. Pobrać obraz z tylnej kamery przez `getUserMedia`, bez mikrofonu. Wykonać klatkę z obrazu wideo i pokazać ją jako podgląd. Zwolnić strumień po wyjściu z kroku lub schowaniu strony. [Specyfikacja Media Capture and Streams](https://www.w3.org/TR/mediacapture-streams/)
2. Na fizycznych telefonach zanotować model, wersję systemu i przeglądarki. Sprawdzić start z przycisku, negację i ponowienie zgody, orientację zdjęcia, ponowne otwarcie aparatu po powrocie oraz czytelność zbliżeń VIN-u i testowego dokumentu. Przy niepowodzeniu ustalić, czy problem dotyczy uprawnień, konkretnej przeglądarki czy rozdzielczości.
3. Utworzyć schemat PostgreSQL jako numerowane migracje SQL. Zacząć od dwóch fikcyjnych spraw i opcji przygotowania wygasłego terminu. Przygotować instrukcję lokalnego uruchomienia, wzór konfiguracji bez wartości sekretów i jedno polecenie do testów. Próbę aparatu można wykonać przed konfiguracją bazy.

## F01 — link, termin i regulamin

Użyć losowego tokenu linku wygenerowanego kryptograficznie. Token umieścić we fragmencie adresu po znaku `#`, a jego skrót zapisać przy sprawie. Kod aplikacji przesyła token w nagłówku autoryzacji do własnego API, nie w ścieżce ani parametrach żądania. Link pozostaje użyteczny po ponownym otwarciu. Nie logować nagłówków żądania, treści zdjęć, pełnych linków ani sekretów. Dla stron inspekcji ustawić `Referrer-Policy: no-referrer`.

Worker sprawdza token przy każdej operacji. Terminy zapisać w UTC, a wyświetlać w polskiej strefie czasowej. Odczyt i zapis są odrzucane, kiedy czas na serwerze osiągnie termin. Regulamin testowy ma stałą wersję. Zapisać chwilę akceptacji i wersję tekstu, ponowienie zachowuje wynik pierwszego zapisu. Przy błędzie aplikacja pozwala ponowić próbę.

## F02 — zdjęcie i podgląd

Przenieść sprawdzony mechanizm aparatu do E2. Pokazać instrukcję, przykład kadru i przycisk widoczny bez przewijania. Przyjąć JPEG do 4 MiB i początkowo do 2048 pikseli na dłuższym boku. Zweryfikować ostrość licznika, VIN-u i dokumentu na próbie z obu telefonów. Gdy zapis nie powiedzie się, pozostawić podgląd gotowy do ponowienia. Gdy użytkownik zamknie stronę przed zatwierdzeniem, będzie mógł wykonać ujęcie ponownie.

Obsłużyć odmowę uprawnienia, brak kamery, anulowanie powtórzenia i powrót do kroku. Interfejs ma wyłącznie podgląd obrazu z aparatu i wykonanie zdjęcia. Kryterium dotyczy normalnego korzystania z aplikacji w testowanej przeglądarce.

## F03 — zapis, odczyt, powrót i podmiana

- Baza trzyma rekord sprawy oraz jedno aktywne odwołanie do zdjęcia na parę sprawa–ujęcie, wymuszone ograniczeniem unikalności. Każda próba zapisu ma własny identyfikator operacji, którego przeglądarka używa ponownie, gdy odpowiedź zaginie. Worker sprawdza rozmiar i format JPEG, a magazyn egzekwuje limit pliku i typu. Pliki przesyłać pojedynczo, z ograniczeniem strumienia do limitu, bez przetwarzania obrazu po stronie Workera. [Limity plików Supabase](https://supabase.com/docs/guides/storage/uploads/file-limits)
- Załadować nowy plik pod osobnym kluczem. Następnie w transakcji PostgreSQL zablokować rekord sprawy, ponownie sprawdzić termin, akceptację i stan, podmienić odwołanie oraz zapisać wynik operacji. Przy niejasnym wyniku zapisu najpierw odczytać jego zapisany stan. Ponowienie zakończonej operacji oddaje jej wynik bez ponownej zmiany zdjęcia. Operacje podmiany tego samego ujęcia rozstrzyga kolejność skutecznych zapisów w bazie.
- Licznik i ekran wznowienia wynikają z zapisanych ujęć. Wygasły link blokuje kolejne odczyty nawet w otwartej karcie. Po odmowie wyczyścić ekran sprawy i zwolnić lokalne podglądy. Ujęcia pobrane wcześniej mogły już zostać zobaczone.
- Stary plik usuwać dopiero po skutecznej podmianie odwołania. Nieudane usunięcie i nieużyty plik po przerwanym zapisie usuwa opiekun podczas sprzątania. Procedura porównuje pliki z rekordami po zamknięciu testów, usuwa pliki testowe z prywatnego magazynu i czyści odpowiadające im rekordy. Opisać ją w README, łącznie z zachowaniem przy częściowym niepowodzeniu.

## F04 — zakończenie i odbiór

Zakończenie wykonać w transakcji wykorzystującej tę samą blokadę sprawy co zapisy zdjęć. Sprawdzić ważność, akceptację i komplet ośmiu różnych typów ujęć. Potwierdzone zakończenie jest powtarzalne dla ważnego linku. Po zakończeniu aplikacja udostępnia potwierdzenie, a zapis zdjęć i ich odczyt przez interfejs klienta są wyłączone.

Testy automatyczne mają objąć dwie niezależne sprawy, upływ terminu przy otwartej sesji, odrzucenie zapisu bez akceptacji, przerwany zapis, ponowienie po utracie odpowiedzi, nieudaną podmianę oraz wyścig zapisu z zakończeniem. Użyć kontrolowanego zegara, żeby sprawdzić ostatnią chwilę ważności i sam moment wygaśnięcia bez czekania pięciu dni. Przy wdrożonej próbie sprawdzić prywatność magazynu, brak cache dla danych spraw i zawartość logów.

Na każdym telefonie przejść F04-KA4 od przygotowanego linku do potwierdzenia po ponownym otwarciu. Wynik zapisać z datą oraz wersjami urządzeń i przeglądarek. Powtórzyć obserwacje dotyczące VIN-u i przycisku według [notatek z testów](wnioski-z-testow.md). Odbiór wymaga przejścia obu ścieżek i potwierdzenia niezmienników N1–N5.

## Stan i następny krok

### Sprawdzenie układu prototypu — 19 listopada 2026

Gotowe w `prototyp.html`: układ mobilny i tabletowy do 720 px szerokości, bez bocznej kolumny; tekst podstawowy 16 px; dolny pasek akcji zdjęcia z uwzględnieniem bezpiecznego obszaru ekranu i zapasem przewijania zależnym od wysokości paska. Większy ekran zachowuje układ tabletowy. Wytyczne zaktualizowano w [DESIGN.md](../DESIGN.md).

Sprawdzono w Chromium przez agent-browser rozmiary 320×568, 390×844, 600×960, 768×1024, 1024×768, 844×390 i 1440×900. Na każdym rozmiarze przeszła ścieżka: akceptacja regulaminu, osiem ujęć demonstracyjnych z podglądem i zatwierdzeniem, galeria, powrót do poprawy VIN-u, zakończenie i dialog pomocy. Brak poziomego przepełnienia; wszystkie akcje zdjęcia mieszczą się w ekranie i mają co najmniej 44 px wysokości. Sprawdzono wizualnie ekran zdjęcia i galerię. To weryfikacja układu w emulowanych rozmiarach, bez testu aparatu i fizycznych urządzeń. F02-KA1–KA4 nadal wymagają odbioru na wskazanych telefonach; zmiana prototypu nie kończy implementacji F02.

F00 w trakcie. [Ekran próby](../proba-aparatu/index.html) jest gotowy lokalnie. Symulacja sprawdziła zrobienie zdjęcia, ponowienie i anulowanie, odmowę dostępu oraz zwolnienie strumienia. Do wykonania pozostają udostępnienie przez HTTPS i próba na fizycznym iPhonie i Samsungu, a następnie konfiguracja bazy, magazynu i danych startowych. F01–F04 oczekują na realizację. Wyniki prób na telefonach dopisać przy realizacji F00.
