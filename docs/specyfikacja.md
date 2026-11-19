# Specyfikacja MVP — Inspekcja online

Wersja 1 · 16 listopada 2026 · Źródła: [brief](../BRIEF.md), [specyfikacja prototypu](../SPECYFIKACJA.md), [prototyp](../index.html), [wytyczne wyglądu](../DESIGN.md), [wyniki testów](wnioski-z-testow.md) i ustalenia z właścicielem projektu.

## 1. Cel i użytkownicy

Inspekcja online ma umożliwić samodzielne wykonanie zdjęć pojazdu na potrzeby ubezpieczenia, bez umawiania wizyty rzeczoznawcy. W MVP uczestnik testu odgrywa rolę osoby, która dostała link do oględzin. W przeglądarce telefonu przechodzi od otwarcia fikcyjnej sprawy do zapisania kompletu zdjęć oraz potwierdzenia zakończenia. Wynik testu pokaże, czy ta ścieżka działa na dostępnych urządzeniach i gdzie uczestnik potrzebuje pomocy.

## 2. Co pokazały testy prototypu

Testowały trzy osoby. Nie ustalono, czy należały do grupy docelowej.

| ID | Obserwacja | Wniosek i zmiana | Do sprawdzenia |
| --- | --- | --- | --- |
| W1 | 3 z 3 osób zatrzymały się przy VIN-ie. Jedna powiedziała, że nie wie, gdzie jest VIN. Powodu zatrzymania pozostałych dwóch nie znamy. | Właściciel dodał ilustrację VIN-u przy szybie. | Czy uczestnik znajduje testowy VIN bez podpowiedzi (E2, F02). |
| W2 | Jedna osoba zasugerowała, aby przycisk „Zrób zdjęcie” był widoczny bez przewijania. | Właściciel przeniósł przycisk wyżej. | Czy przycisk jest widoczny po otwarciu kroku na obu telefonach (E2, F02). |
| W3 | Według relacji właściciela uczestnicy odnajdywali się w interfejsie, instrukcje były jasne, a po kroku VIN nie było dalszych problemów. | Prototyp wyznacza kolejność kroków i instrukcje ujęć. | Czy uczestnik kończy całą ścieżkę w działającym MVP (F04). |

Poprawek z W1 i W2 jeszcze nie przetestowano.

## 3. Zakres MVP

**Główna ścieżka:** uczestnik otwiera indywidualny link do fikcyjnej sprawy, akceptuje regulamin testowy, robi i zatwierdza osiem zdjęć, sprawdza komplet, w razie potrzeby poprawia ujęcie i kończy inspekcję.

**Czas:** trzy tygodnie. Szacunek 24–27 godzin zakłada pięć godzinnych wieczorów i 3–4 godziny łącznie w każdy weekend.

- Przed testem przygotowuje się fikcyjne sprawy z indywidualnymi linkami. Link wygasa po pięciu dniach od zlecenia. Dostęp nie wymaga konta ani kodu SMS.
- W kroku ujęcia uczestnik uruchamia aparat telefonu, robi zdjęcie i od razu widzi je w podglądzie. Aplikacja nie udostępnia galerii, wyboru pliku ani wcześniej zrobionych zdjęć. „Zatwierdź zdjęcie” zapisuje zdjęcie na serwerze. „Powtórz” umożliwia wykonanie nowego ujęcia.
- Każde zapisane ujęcie i zaakceptowany regulamin są dostępne po ponownym otwarciu ważnego linku. Licznik odzwierciedla stan potwierdzony przez serwer.
- Użytkownik może przejrzeć osiem miniatur i poprawić pojedyncze ujęcie. Po zapisaniu przez serwer stanu zakończenia aplikacja pokazuje potwierdzenie. Zakończona sprawa jest dostępna do odczytu potwierdzenia do wygaśnięcia linku.

**Później:** automatyczne generowanie i wysyłka linków oraz przypomnienia, ponieważ do testu wystarczą przygotowane linki; panel pracownika i ocena zdjęć przez AI, ponieważ test dotyczy ścieżki klienta; środowisko produkcyjne, ponieważ test korzysta ze spraw i danych fikcyjnych.

## 4. Role i uprawnienia

| Rola | Dostęp i działanie |
| --- | --- |
| Osoba z ważnym linkiem | Widzi jedną sprawę, akceptuje regulamin, zapisuje lub zastępuje ujęcia i kończy inspekcję. Po zakończeniu widzi potwierdzenie. |
| Opiekun testu | Przygotowuje fikcyjne sprawy, przekazuje linki testerom i sprząta dane po teście. Korzysta z narzędzi środowiska testowego poza interfejsem klienta. |
| Osoba bez ważnego linku | Otrzymuje komunikat o braku dostępu. Nie ma dostępu do danych sprawy, zdjęć ani zapisów. |

## 5. Ekrany i ścieżki

| ID | Ekran | Zachowanie | Karta |
| --- | --- | --- | --- |
| E1 | Ekran powitalny | Dane fikcyjnego pojazdu, termin, lista ujęć oraz regulamin i jego akceptacja. | F01 |
| E2 | Dobry kadr. Krok po kroku. | Instrukcja, przykład kadru, aparat, podgląd i zatwierdzenie. Powrót prowadzi do pierwszego brakującego ujęcia. | F02, F03 |
| E3 | Osiem zdjęć. Komplet. | Osiem podpisanych miniatur i dane pojazdu. Można poprawić pojedyncze ujęcie albo zakończyć sprawę. | F03, F04 |
| E4 | Potwierdzenie | Dane pojazdu i potwierdzenie zakończenia. Ten ekran zobaczy osoba ponownie otwierająca ważny link. | F04 |
| E5 | Link niedostępny | Komunikat przy braku ważnego dostępu, również gdy upłynął termin podczas otwartej sesji. | F01 |

Kolejność ujęć na E2: przód, tył, lewy bok, prawy bok, licznik, VIN, pierwsza i druga strona dowodu rejestracyjnego. Po poprawie ujęcia z E3 użytkownik wraca do podsumowania. Ilustracja przy VIN-ie pokazuje przygotowane miejsce przy dolnej krawędzi przedniej szyby, które sprawdzamy w teście.

## 6. Model danych

| Encja | Pole | Znaczenie i typ | Kto ustawia | Dostęp |
| --- | --- | --- | --- | --- |
| Sprawa | Identyfikator | Wymagany, unikalny identyfikator, np. `TEST-001`. | Przygotowanie spraw testowych | Serwer |
| Sprawa | Dane pojazdu | Wymagane teksty, np. „Auto testowe”, „Model 01”, „TEST 01”. | Przygotowanie spraw testowych | E1, E3, E4 |
| Sprawa | Data zlecenia i termin | Wymagane daty z czasem. Termin przypada po pięciu dniach od zlecenia. | Serwer i dane startowe | Termin na E1; sprawdzany przez serwer |
| Sprawa | Dostęp z linku | Wymagane powiązanie indywidualnego linku z jedną sprawą. | Przygotowanie spraw testowych | Sekret zna posiadacz linku; weryfikuje go serwer |
| Sprawa | Akceptacja regulaminu | Pusta do akceptacji. Po jej zapisie stan pozwala wznowić zdjęcia. | Serwer po działaniu użytkownika | Własna sprawa |
| Sprawa | Stan zakończenia | Otwarta lub zakończona. | Serwer | Własna sprawa |
| Ujęcie | Sprawa i rodzaj | Wymagana para wskazująca jedną sprawę i jedno z ośmiu ujęć. | Serwer według kroku | Własna sprawa |
| Ujęcie | Zdjęcie | Wymagany plik i odwołanie do prywatnego magazynu, zapisane po zatwierdzeniu. | Serwer po zatwierdzeniu | Własna sprawa przez aplikację |

Sprawa ma od zera do ośmiu zatwierdzonych ujęć. Kolejne zatwierdzenie dla tej samej pary sprawa–rodzaj zastępuje ujęcie po udanym zapisie. Ponowienie żądania po utracie odpowiedzi nie zwiększa licznika. Nieudana podmiana zachowuje poprzednie ujęcie. Podgląd roboczy nie liczy się do kompletu i nie wraca po zamknięciu sesji. Fizyczne czyszczenie rekordów i plików po teście jest zadaniem opiekuna testu. Wygaśnięcie linku zamyka dostęp użytkownika.

## 7. Ochrona danych i bezpieczeństwo

MVP jest przeznaczone do fikcyjnych danych. W zdjęciach testowych używamy oznaczonych rekwizytów VIN-u i dokumentu. Dane na zdjęciach, które mogłyby wskazać rzeczywistą osobę lub pojazd, należy zasłonić albo wykadrować. W produkcji ten sam rodzaj plików może zawierać dane osobowe. Wprowadzenie rzeczywistych spraw wymaga osobnej decyzji o środowisku i obsłudze danych.

Cloudflare obsługuje ruch aplikacji, a Supabase przechowuje fikcyjne dane w PostgreSQL i zdjęcia w prywatnym magazynie. W Fazie A trzeba sprawdzić dostępność usług na koncie testowym, region i warunki. AI nie wchodzi do zakresu MVP.

| ID | Niezmiennik | Jak sprawdzić |
| --- | --- | --- |
| N1 | Ważny link daje dostęp tylko do jednej sprawy. Kontrolę wykonuje serwer przy odczycie i zapisie. | Użyć dwóch fikcyjnych spraw i sprawdzić odmowę dostępu do drugiej, w tym do jej zdjęć. |
| N2 | Od chwili wygaśnięcia serwer odrzuca dalsze odczyty sprawy i plików oraz zapisy. | Otworzyć już wygasłą sprawę i wykonać operację w sesji rozpoczętej przed wygaśnięciem. |
| N3 | Zapis zdjęć wymaga akceptacji regulaminu i otwartej sprawy. Zakończenie wymaga ośmiu zapisanych ujęć. | Sprawdzić odmowę zapisu bez akceptacji i po zakończeniu oraz odmowę zakończenia przy 7/8. |
| N4 | Zdjęcia są prywatne, a logi nie zawierają zdjęć, pełnych linków do spraw ani kluczy. | Sprawdzić konfigurację magazynu i logi po udanej operacji i błędzie. |
| N5 | Interfejs dodaje zdjęcie tylko przez aparat w bieżącym kroku. | Na iPhonie i Samsungu sprawdzić zrobienie i powtórzenie zdjęcia, anulowanie oraz odmowę dostępu do aparatu. W żadnej ścieżce nie pojawia się wybór zdjęcia z galerii. |

Każdy z ważnym linkiem może wejść do sprawy, jeśli link zostanie przekazany dalej. Kryterium N5 dotyczy ścieżki w obsługiwanej przeglądarce. Wiarygodność materiału dowodowego i sposób potwierdzania pochodzenia zdjęcia w procesie produkcyjnym wymagają osobnego ustalenia.

## 8. Kierunek techniczny

Cloudflare Workers jest proponowanym miejscem uruchomienia interfejsu i obsługi spraw. Na potrzeby MVP kierunek to PostgreSQL w Supabase i prywatny Supabase Storage. Właściciel wskazał, że firma nie akceptuje Supabase w produkcji. Produkcyjny dostawca PostgreSQL pozostaje do wyboru. Azure jest jedną z opcji.

W Fazie A ustalić sposób dostępu do bazy i magazynu, rozdzielając obsługę rekordów od plików, sposób przygotowania spraw i sprzątania zdjęć oraz sposób wygasania dostępu do plików. Zaplanować zmiany schematu bazy, limity walidacji zdjęć i obsługę nieudanych zapisów. Sprawdzić dostęp do aparatu przez HTTPS na fizycznym iPhonie z Safari i Samsungu z Chrome przed pracą nad resztą ścieżki zdjęć. Daty i treść ekranu są w języku polskim.

## 9. Wymagania ogólne

Wygląd oraz komponenty według [DESIGN.md](../DESIGN.md). Przycisk „Zrób zdjęcie” jest dostępny bez przewijania po wejściu w krok na obu telefonach testowych. Instrukcja i przykład kadru są czytelne. Sterowanie dotykowe, kontrast, widoczny fokus i komunikaty błędów podlegają sprawdzeniu przy odbiorze.

Podczas zapisu ekran pokazuje, że operacja trwa. Awaria połączenia kończy się komunikatem i możliwością ponowienia zapisu. Ujęcie jest zaliczane po potwierdzeniu z serwera. Gdy dostęp do aparatu jest niedostępny, użytkownik dostaje wskazówkę dotyczącą uprawnień i może ponowić próbę.

## 10. Funkcje i kolejność

| ID | Funkcja | Priorytet | Złożoność | Zależy od |
| --- | --- | --- | --- | --- |
| F00 | [Fundament i środowisko testowe](funkcje/F00-fundament.md) | MVP-1 | Wysoka | — |
| F01 | [Link i regulamin](funkcje/F01-link-i-regulamin.md) | MVP-1 | Wysoka | F00 |
| F02 | [Aparat i podgląd ujęcia](funkcje/F02-aparat-i-podglad.md) | MVP-1 | Wysoka | F00, F01 |
| F03 | [Zapis, wznowienie i poprawa zdjęć](funkcje/F03-zapis-i-wznowienie.md) | MVP-1 | Wysoka | F01, F02 |
| F04 | [Zakończenie i odbiór ścieżki](funkcje/F04-zakonczenie.md) | MVP-1 | Średnia | F03 |

## 11. Decyzje i założenia

- DEC-1. MVP obsługuje fikcyjne sprawy, a odbiór obejmuje ścieżkę od otwarcia linku do zakończenia. Źródło: właściciel i zatwierdzony zakres.
- DEC-2. Zdjęcia są robione w bieżącym kroku. Import zdjęć z galerii lub pliku jest poza zakresem i nie jest ścieżką awaryjną. Źródło: właściciel.
- DEC-3. Testy na fizycznym iPhonie i Samsungu. Źródło: właściciel.
- DEC-4. Supabase można wykorzystać w teście. Firma właściciela nie dopuszcza go w produkcji. Dostawca produkcyjnego PostgreSQL pozostaje otwarty. Źródło: właściciel.
- DEC-5. Ważność linku przez pięć dni i brak dodatkowego kodu SMS. Źródło: specyfikacja prototypu i zatwierdzony zakres MVP.
- A1. Budżet 24–27 godzin zakłada 3–4 godziny łącznie na weekend. Nakład zweryfikuje plan techniczny.
- A2. Cloudflare Workers i prywatny Supabase Storage to proponowany kierunek wykonania testowej wersji. Sposób ich użycia zweryfikuje Faza A.
- A3. Do testu używamy regulaminu oznaczonego jako przykładowy oraz przygotowanego arkusza z fikcyjnym VIN-em i kartami dowodu. Opiekun usuwa sprawy i pliki po zakończeniu prób.

## 12. Pytania otwarte i ryzyka

- Q1. Konkretne modele, wersje systemów i przeglądarek testowych. Zapisać przed próbą aparatu; właściciel.
- Q2. Parametry zdjęć, reguły przechowywania i procedura czyszczenia danych testowych. Ustalić w Fazie A przed F03; autor planu i właściciel.
- Q3. Produkcyjny dostawca PostgreSQL i magazynu zdjęć. Decyzja przed planowaniem produkcji; nie blokuje MVP.
- R1. Aparat albo układ E2 zachowuje się inaczej na dwóch telefonach. Wczesna próba przez HTTPS pozwoli ocenić wykonalność przed integracją zapisu.
- R2. Ilustracja VIN-u i wyżej umieszczony przycisk nie przeszły powtórnego testu z uczestnikiem. Powtórzyć próbę, zachowując oddzielny zapis obserwacji.
- R3. Słabe połączenie w miejscu wykonywania zdjęć może przerwać zapis. Sprawdzić ponowienie i zachowanie poprzedniego zdjęcia po nieudanej podmianie.

## 13. Następne kroki

Przed testami właściciel przygotowuje oba telefony, arkusz rekwizytów i dostęp do testowych usług. Sekrety przekazuje przez konfigurację środowiska, a do repozytorium trafiają wyłącznie nazwy wymaganych zmiennych.

1. **Faza A.** „Na podstawie `docs/specyfikacja.md` i kart przygotuj `docs/plan.md`. Rozpisz zadania na trzy tygodnie i wskaż, jak wcześnie sprawdzić aparat na obu telefonach oraz jak testować granice dostępu.”
2. **Faza B.** „Zbuduj kolejną kartę według `docs/plan.md` i jej kryteriów. Użyj fikcyjnych spraw. Odnotuj wynik w planie i README.”
3. **Faza C.** „Sprawdź kryteria i niezmienniki z kart oraz odbiór całej ścieżki na obu telefonach. Zapisz wyniki wraz z wersjami systemów i przeglądarek.”

Główne materiały: `BRIEF.md`, `SPECYFIKACJA.md`, `DESIGN.md` i `index.html`. Pakiet do budowy: niniejsza specyfikacja, karty w `docs/funkcje/`, wnioski z testu w `docs/wnioski-z-testow.md` oraz `AGENTS.md` i `README.md`. Plan techniczny powstanie w Fazie A.
