# SPEC.md — Inspekcja online

## 1. Aplikacja w jednym zdaniu

"Inspekcja online" prowadzi klienta krok po kroku przez proces wykonania ośmiu zdjęć pojazdu wymaganych do zawarcia umowy ubezpieczenia.

## 2. Kontekst użytkownika i ograniczenia

- Jeżeli Ubezpieczyciel uzna, że przed zawarciem umowy ubezpieczenia konieczne jest przeprowadzenie oględzin pojazdu, klient musi oczekiwać na kontakt ze strony rzeczoznawcy w celu ustalenia terminu oględzin. Po ich przeprowadzeniu rzeczoznawca przekazuje dokumentację fotograficzną Ubezpieczycielowi, który na jej podstawie podejmuje decyzję o dalszych krokach w procesie zawierania umowy ubezpieczenia.
- Rzeczoznawca ma 24 godziny na kontakt z klientem oraz później 24 na odesłąnie zdjęć wraz z protokołem. Średni czas procesu od momentu zlecenia oględzin do uzyskania wyniku to ok 3-4 dni.
- Ubezpieczyciel ma ograniczoną skalę wykonywania oględzin przed ubezpieczeniem samochodu - zasięg to cała Polska, ograniczona licbza rzeczoznawców.
- W docelowym procesie system automatycznie generuje linka i wysyła do Klienta. Po odesłaniu zdjęć system automatycznie analiuzje czy zdjęcia zawierają elementy wymagające dalszej weryfikacji (np. samochód jest uszkodzony, brak wszystkich stron pojazdu, niezgodność przebiegu z deklarowanym itp).
- Dzięki aplikacji Klient może szybko wykonać 8 prostych zdjęć i ubezpieczyć samochód bez konieczności oczekiwania i umawiania się z rzeczoznawcą.
- Dzięki aplikacji Ubezpieczyciel ogranicza koszty (rzecznzawca, zespół obsługujący proces) oraz zwiększa skale działania procesu.

### Użytkownicy i warunki korzystania

- **Kto wykonuje zdjęcia.** Z założenia zdjęcia wykonuje osoba zawierająca umowę ubezpieczenia. W praktyce może je wykonać osoba, której numer telefonu poda kupujący ubezpieczenie.
- **Miejsce i łączność.** Zdjęcia będą najczęściej wykonywane na parkingach. Dokładna lokalizacja osoby wykonującej zdjęcia i jakość połączenia w tym miejscu są nieznane.
- **Urządzenia i przeglądarki.** Aplikacja ma działać na każdym smartfonie z Androidem lub iOS, we wszystkich popularnych przeglądarkach, w szczególności w Chrome, Edge, Firefox i Safari.
- **Termin.** Link wygasa po pięciu dniach od zlecenia oględzin. Po tym czasie nie można otworzyć sprawy ani dokończyć oględzin rozpoczętych przed upływem terminu.
- **Dostęp.** Osoba, która otrzymała ważny link, może otworzyć sprawę i wykonać zdjęcia bez dodatkowego potwierdzenia kodem SMS.

## 3. Zakres

| Must-have | Nice-to-have | Poza zakresem prototypu (powód) |
|---|---|---|
| Wejście z linku do sprawy i akceptacja regulaminu | Spersonalizowany komunikat witający klienta                | Generowanie i wysyłka linków  |
| Instrukcja i przykład kadru dla każdego z ośmiu ujęć, dodanie zdjęcia, podgląd, poprawa i zatwierdzenie | Animowane zdjęcia demonstracyjne do przejścia ścieżki bez używania aparatu  | Podgląd zakończonej inspekcji    |
| Akceptacja regulaminu przed rozpoczęciem wykonywania zdjęć jest obligatoryjnie do zaznaczenia (nie można pominąć tego kroku).    | — | — |
| Klient wykonuje każde zdjęcie aparatem telefonu podczas oględzin. Wybór zdjęć z galerii jest niedostępny. | Uruchomienie aparatu i wykonanie zdjęcia bezpośrednio w oknie aplikacji webowej | Nagrywanie filmów — do oględzin wymagany jest komplet ośmiu zdjęć |
  | Aplikacja działa na każdym smartphonie na Chrome/Firefox/Edge/Safari bez koniecznosci instalacji czegokolwiek na smarphonie        | — | Aplikacja z AppStore/GooglePlay. Badania pokazują, że uzytkownicy niechętnie instalują aplikacje na swoich telefonach.     |

## 4. Ekrany w kolejności głównej ścieżki

Główna ścieżka: klient otwiera link do swojej sprawy, akceptuje przykładowy regulamin, dodaje i zatwierdza osiem zdjęć, sprawdza komplet i kończy demonstrację.

1. **Ekran powitalny**: Klient widzi dane swojego pojazdu, datę zlecenia, termin i listę ujęć jakie będzie musiał wykonać. Zapoznaje się z regulaminem i zaznacza akceptację, aby odblokować „Rozpocznij zdjęcia”.
2. **Dobry kadr. Krok po kroku.** Klient widzi instrukcję, przykład kadrowania i postęp. Wybiera „Wykonaj zdjęcie”. Sprawdza podgląd, w razie potrzeby wybiera „Powtórz”, a potem „Zatwierdź zdjęcie”.
3. **Osiem zdjęć. Komplet.** Klient przegląda osiem podpisanych miniatur. Może wrócić do wybranego ujęcia, a po sprawdzeniu zestawu wybiera „Zapisz i wyślij”.
4. **Zapisano i wysłano.** Klient widzi dane pojazdu, liczbę zdjęć i informację, że zakończył oględziny. 

## 5. User stories must-have

### US1 · Otwarcie sprawy i akceptacja regulaminu

Jako klient chcę otworzyć otrzymany link na telefonie i sprawdzić dane pojazdu oraz zasady oględzin, żeby zacząć od właściwej sprawy.

- **K1.** Link otwiera ekran przygotowania dla wskazanego pojazdu.

  **Sprawdzam:** otwieram link do sprawy w nowej karcie na telefonie. **Zaliczone, gdy** od razu widzę markę, model, numer rejestracyjny i termin z tej sprawy oraz przykładowy regulamin.

- **K2.** Wykonywanie zdjęć można rozpocząć po zaakceptowaniu regulaminu.

  **Sprawdzam:** sprawdzam przycisk „Rozpocznij zdjęcia” przed zaznaczeniem pola, po zaznaczeniu i po odznaczeniu. **Zaliczone, gdy** przycisk jest aktywny wyłącznie przy zaznaczonym polu, a jego dotknięcie otwiera ujęcie „Przód pojazdu”.

### US2 · Wykonanie i zatwierdzenie ośmiu ujęć

Jako klient chcę widzieć instrukcję i podgląd każdego zdjęcia, żeby samodzielnie przygotować komplet do oględzin.

- **K1.** Każdy krok pokazuje nazwę ujęcia, instrukcję i przykład kadrowania.

  **Sprawdzam:** przechodzę wszystkie kroki. **Zaliczone, gdy** dla każdego widzę te trzy elementy, a ujęcia następują w kolejności: przód, tył, lewy bok, prawy bok, licznik, VIN, pierwsza strona dowodu rejestracyjnego, druga strona dowodu rejestracyjnego.

- **K2.** Zdjęcie wykonane telefonem pojawia się w podglądzie i można je wymienić przed zatwierdzeniem.

  **Sprawdzam:** dotykam „Wykonaj zdjęcie”, robię zdjęcie, wybieram „Powtórz” i najpierw anuluję wybór, a potem dodaję inne zdjęcie. **Zaliczone, gdy** po anulowaniu nadal widzę poprzednie zdjęcie, a po ponownej próbie podgląd pokazuje nowe.

- **K3.** Licznik uwzględnia wyłącznie zatwierdzone ujęcia, a podsumowanie otwiera się po zebraniu całego kompletu.

  **Sprawdzam:** przy stanie 7/8 dodaję ósme zdjęcie i zatwierdzam je po obejrzeniu podglądu. **Zaliczone, gdy** przed zatwierdzeniem widzę 7/8 i pozostaję na ekranie ujęcia, a po zatwierdzeniu widzę podsumowanie 8/8.

### US3 · Sprawdzenie kompletu i zakończenie demonstracji

Jako klient chcę sprawdzić i poprawić zdjęcia przed zakończeniem, żeby mieć komplet przypisany do właściwego pojazdu.

- **K1.** Podsumowanie pokazuje dane pojazdu i osiem podpisanych miniatur. Klient może poprawić pojedyncze ujęcie.

  **Sprawdzam:** wybieram miniaturę „Licznik”, dodaję inne zdjęcie i je zatwierdzam. **Zaliczone, gdy** wracam do podsumowania tego samego pojazdu, zmieniła się tylko miniatura licznika, a licznik nadal pokazuje 8/8.

- **K2.** „Zapisz i wyślij” kończy demonstrację i wyświetla potwierdzenie.

  **Sprawdzam:** wybieram „Zapisz i wyślij” przy otwartym panelu sieciowym przeglądarki. **Zaliczone, gdy** potwierdzenie wskazuje właściwy pojazd, osiem zdjęć i informację o symulacji, a panel sieciowy nie pokazuje żądania przesyłającego zdjęcia.

**Odbiór całej ścieżki.** Klient otwiera link na telefonie i wykonuje osiem ujęć bez podpowiedzi testera. Test jest zaliczony, gdy klient dochodzi do potwierdzenia, a tester uznaje wszystkie osiem zdjęć za zgodne z instrukcjami. Na każdym telefonie z uzgodnionej listy tester sprawdza też, czy zdjęcie wykonane aparatem otwiera się w podglądzie (US2, K2).

## 6. Kierunek budowy

- **Dane wspólne dla osób lub urządzeń** — nie, klient ma dostep i iwdzi tylko swoją sprawę. Wykonanie oględzin przez Klienta zamyka sprawę, Klient nie ma możliwości powrotu do sprawy.
- **Płatne API z własnym kluczem** — nie.
- **Kierunek** — front dla klienta będzie częścią większej platformy do zarządzania oględzinami online. Platfroma będzie generować linki oraz udostępniać front dla pracowników, który będą zapoznawać się z wybraną częścią przesłanych wyników. Ponadto platforma będzie automatycznie (z wykorzystaniem AI) analizować przesłane zdjęcia.
- **Co świadomie pomijamy w budowie** — serwer, bazę i logowanie. Do przejścia US1–US3 wystarczają fikcyjne sprawy i stan jednej karty.
- **Co przenosimy poza zakres** — wysyłkę zdjęć, powrót do sprawy w ciągu pięciu dni, przypomnienia, panel pracownika i ocenę zdjęć przez AI.
- **Warunek zmiany kierunku** — wymaganie trwałego powrotu do sprawy po zamknięciu karty, kontynuacji z innego urządzenia albo udostępnienia kompletu pracownikowi. Współdzielenie sprawy wymaga warstwy serwerowej z kontrolą dostępu, trwałym zapisem stanu oraz przechowywaniem zdjęć.

## 7. Wygląd

**Źródło wyglądu** — [design.md](design.md). Biały panel zadania, lawendowe akcje drugorzędne, fioletowe CTA i dwubarwne wzory kadrów prowadzą klienta przez oględziny. [Prototyp](prototyp.html) stosuje te zasady na wszystkich ekranach.
