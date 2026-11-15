## Visual DNA

1. **Biel, lawenda, fiolet i punktowa fuksja.** Białe pola pracy na niemal białym tle, lawendowe akcje drugorzędne, głęboki fiolet nagłówka hero i stopniowany fiolet głównego CTA. Fuksja pojawia się w detalach piktogramów, nazwach produktów i narożnej wstędze rabatowej.
2. **Duży bezszeryfowy tekst z oszczędnym pogrubieniem.** Wyśrodkowany slogan i duże tytuły sekcji mają wspólną linię bazową dla fragmentów regularnych i pogrubionych. Treść użytkowa jest mniejsza, ciemna i utrzymana w jednym rytmie.
3. **Panel zadania jako środek ciężkości.** W hero wzrok prowadzą duże zakładki z piktogramami do jasnej karty wyceny z szerokim CTA. Komunikat kampanii ma osobną przestrzeń. Na telefonie ustępuje miejsca formularzowi i trafia pod niego.
4. **Ilustracja związana z czynnością.** Samochód, dom, bagaż, serca, prezent, kalendarz i stoper to rozpoznawalne, konturowe rysunki w fiolecie z różowymi detalami. Fotografia jest przede wszystkim redakcyjna, a nie dominującym tłem interfejsu.
5. **Głębia skupiona wokół istotnych powierzchni.** Hero ma wyraźny rozproszony cień. Karty produktów mają subtelniejszy cień i delikatny kontur. Jasne geometryczne motywy przy krawędziach zostawiają środek strony spokojny.

## Analiza referencji

### Kolor i powierzchnie

| Rola w referencji | HEX | Podstawa |
| --- | --- | --- |
| Fiolet nagłówka hero i tekstu akcji drugorzędnej | `#501E82` | Pomiar |
| Fiolet linku formularza i początek gradientu CTA | `#781E82` | Pomiar |
| Kolejne barwy gradientu CTA | `#8B2380`, `#A82A7C`, `#9525A2` | Pomiar, kierunek poziomy |
| Lawenda skrótów obsługi i przycisków drugorzędnych | `#F2EBFA` | Pomiar |
| Biel kart, zakładek i pól | `#FFFFFF` | Pomiar |
| Grafit nagłówków sekcji i konturu wyszukiwarki | `#3E3E3E` | Pomiar |
| Tekst bazowy na poziomie kontenera | `#000000` | Pomiar, lokalnie występuje grafit |
| Kontur zakładek | `#4D267D` | Pomiar |
| Kontur pól i kart oferty | `#DADADA`, `#F1F1F1` | Pomiar |
| Fuksja akcentów kampanii i ilustracji | ok. `#EC008C` | Szacunek |
| Tło poniżej hero i pasek kontaktowy | ok. `#F9F7FA`, `#EDE0F6` | Szacunek, tło sekcji ma lokalne warianty |

### Typografia

Wartości w kolumnie „Stopień” mają format rozmiar / interlinia w px. Plus Jakarta Sans i Realist mają w referencji rezerwę Arial, Helvetica, sans-serif. Zapis w tabeli dotyczy konkretnych ról w badanym widoku.

| Rola | Rodzina | Stopień | Grubość | Podstawa |
| --- | --- | --- | --- | --- |
| Slogan hero, desktop | Realist | 44 / 44 | 400, wyróżnienia 700 | Pomiar |
| H2 oferty, korzyści, opinii | Plus Jakarta Sans | 55 / 55, korzyści 55 / 70,4 | 400, wyróżnienia 700 | Pomiar |
| H2 bloga i powtórzonej wyceny | Realist | 55 / 55 | 400 i 700 | Pomiar |
| H1 i główne H2 na telefonie | Zależnie od sekcji | 28 / 35,84 | 400 i 700 | Pomiar |
| Tytuł korzyści | Plus Jakarta Sans | 20 / 25,6 | 800 | Pomiar |
| Tytuł karty wyceny | Plus Jakarta Sans | ok. 28–30 / 36 | regularna i pogrubiona | Szacunek |
| Tekst bazowy | Plus Jakarta Sans | 15 / 25,2 | 400 | Pomiar |
| Pole i główne CTA | Plus Jakarta Sans | 16 / 25,2 | pole 400, CTA 600 | Pomiar |
| CTA kart i skróty obsługi | Plus Jakarta Sans | 14 / 25,2 | odpowiednio 600 i 700 | Pomiar |
| Link prawny formularza | Plus Jakarta Sans | 12 / 18 | 800 | Pomiar |

### Geometria i hierarchia

Przy 1440 px główny kontener miał 1280 px. Wewnątrz hero rząd roboczy miał 1160 px, a biała karta 440 px szerokości. Pola i CTA mierzyły 392 × 64 px, padding karty wynosił 40 px w pionie i 24 px po bokach. Pola dzieliło 8 px, a odstęp nad CTA wynosił ok. 32 px. Karta miała promień 16 px, a pola i główny CTA po 6 px. Zakładki o szerokości ok. 89 px miały promień 8 px i kontur 1 px. Aktywna zakładka była o 8 px niższa i przesunięta o 8 px w dół.

| Sekcja | Obserwacja i pomiary |
| --- | --- |
| Nagłówek | Lawendowy pasek kontaktowy o wysokości 40 px. Poniżej logo, wyszukiwarka w kapsule o wysokości 64 px i promieniu 48 px, okrągła kontrolka dostępności, rozwijane akcje Agenta i Szkód, gradientowe menu z ikoną. |
| Hero | Wyśrodkowany slogan. Niżej karta wyceny z czterema zakładkami ikonowymi i narożną wstęgą, obok kampania o wymiarach 600 × 300 px w zbadanym stanie. Formularz z dwoma polami, przełącznikiem potwierdzenia, linkiem prawnym i pełnoszerokim CTA. |
| Skróty obsługi | Pięć równorzędnych lawendowych kafli w rzędzie. Promień 8 px, ok. 8 px między kaflami i ok. 80 px od dołu karty hero do początku rzędu. |
| Oferta | Pięć kart po 224 × 291 px, z odstępem 16 px. Białe powierzchnie, promień 8 px, padding 15 px, cienki kontur, duży rysunek, krótka etykieta w fuksji i fioletowe CTA o wysokości ok. 41 px. |
| Korzyści | Trzy bloki ikona–tytuł–opis we wspólnym białym panelu. Akcja „Dowiedz się więcej” pod panelem. |
| Opinie | Dwie widoczne karty o szerokości po 592 px i odstępie 32 px na desktopie. Biały cytat z dużymi jasnymi cudzysłowami i wydzielony lawendowy podpis z awatarem. Osobna informacja o pochodzeniu opinii. |
| Blog | Wyróżniony artykuł w podziale 50/50, zdjęcie po lewej i tekst po prawej. Niżej trzy mniejsze kafle z datą i tytułem. |
| Domknięcie | Powtórzenie wyceny OC/AC, następnie stopka z logo i hasłem, kontaktem i pogrupowanymi linkami. Na desktopie boczne skróty pomocy, na telefonie pływający przycisk czatu. |

Zmierzony cień karty wyceny to `0 -2px 16px 2px rgba(0,0,0,.06), 0 16px 64px 10px rgba(0,0,0,.14)`. Aktywna zakładka ma `0 4px 48px rgba(0,0,0,.25)`, karta produktu `0 24px 32px -24px rgba(0,0,0,.24)`. Pola i CTA są płaskie.

### Responsywność, interakcje i media

- **Pomiar.** Na granicy 767/768 px H1 zmieniał się z 28 na 44 px, a pola i główne CTA z 50 na 64 px wysokości. Przy 390 px kontener miał 350 px przy bocznych marginesach 15 px i obszarze treści 380 px. Wnętrze formularza miało 302 px, a zakładki wypełniały jego zewnętrzną szerokość.
- **Pomiar.** Przy 991 px hero było ułożone pionowo, przy 992 px kampania była już obok karty. Próbki szerokości kontenera wynosiły 450 px przy 600 i 767 px, 738 px przy 768–991 px, 962 px przy 992–1279 px, 1160 px przy 1280–1360 px i 1280 px przy 1440 px. Zakresy między próbkami opisują zaobserwowane wartości. Dokładna granica wejścia na 1280 px szerokości kontenera oraz próg wcześniejszego ograniczenia do 450 px pozostają nieustalone.
- **Obserwacja.** Telefon zachowuje górny pasek kontaktowy, a wyszukiwarkę zwija do kontrolki ikonowej. Tytuły łamią się naturalnie. Blog układa zdjęcie nad tekstem, a oferta i opinie pokazują pojedyncze karty w karuzeli. Opinie na telefonie mają kropki nawigacyjne. Na desktopie w drzewie dostępności dostępne są strzałki karuzeli i stan nieaktywnej strzałki na początku.
- **Pomiar i obserwacja.** Zakładka sygnalizuje wybór położeniem i cieniem. Obliczone przejścia to 300 ms dla zakładek, 500 ms dla wybranych akcji lawendowych i 1000 ms dla tła gradientowych CTA, z `ease` w zbadanych kontrolkach. Są to deklarowane czasy, a efekt końcowy hover i czas przesunięcia karuzeli pozostają niezweryfikowane.
- **Obserwacja.** Ikony użytkowe (kalendarz, telefon, lupa, szewron) są proste. Ilustracje produktowe używają większych, dwubarwnych konturów. Grafiki kampanii mają własny układ ilustracji i tekstu. Blog pokazuje fotografie rzeczywistych sytuacji, a opinie używają rysunkowych awatarów.

## System projektowy

### Design principles

- **Najpierw czynność.** Pierwszy ekran wyjaśnia cel i prowadzi do najbliższej akcji. W oględzinach główną ilustracją jest wzór wymaganego kadru, a centralną powierzchnią bieżący krok.
- **Jedno źródło mocnego kontrastu.** Gradient prowadzi do najważniejszej akcji w danym obszarze. Fuksja podkreśla detal ilustracji lub element orientacyjny.
- **Przewidywalna kompozycja.** Wspólna oś dla tytułu, opisu, pól i akcji. Wyśrodkowany krótki wstęp oraz tekst zadania i formularze wyrównane do lewej.
- **Przyjazny język użytkowy.** Nazwa przycisku mówi, co się wydarzy. Instrukcja opisuje czynność, a komunikat o problemie podaje następną dostępną akcję.

### Color tokens

| Token | Wartość | Użycie |
| --- | --- | --- |
| `brand` | `#501E82` | Nagłówek wiodący, tekst na lawendzie, link, obrys fokusu na jasnej powierzchni |
| `action` | `#781E82` | Jednolite tło CTA i kolor rezerwowy gradientu |
| `accent` | `#EC008C` | Punktowy detal graficzny, szacunek przyjęty jako token |
| `surface-tint` | `#F2EBFA` | Akcja drugorzędna, podpis, tło informacji |
| `surface` / `canvas` | `#FFFFFF` / `#F9F7FA` | Karty i tło aplikacji, canvas pochodzi z szacunku |
| `text` / `text-muted` | `#3E3E3E` / `#616161` | Treść główna i pomocnicza |
| `border-subtle` / `border-control` | `#DADADA` / `#767676` | Podziały dekoracyjne i granica pola |
| `error` / `error-surface` | `#A61946` / `#FFF0F4` | Błąd z ikoną i opisem |
| `success` / `success-surface` | `#216846` / `#EAF6EF` | Potwierdzenie z ikoną i opisem |
| `disabled-surface` / `disabled-text` | `#EEEAF0` / `#68616E` | Niedostępna kontrolka |

Gradient akcji biegnie poziomo od `#781E82` przez `#8B2380` do `#9525A2`. To uproszczona wersja gradientu referencji. Stosuj białą etykietę i sprawdź kontrast na całym przebiegu, również w stanie hover. Gradient identyfikacyjny z mocną fuksją należy do oprawy graficznej.

### Typography scale

Plus Jakarta Sans obsługuje cały interfejs. Dla ekranów procesu użyj jednej rodziny. W szerokim hero marketingowym dopuszczalny jest Realist, jeśli projekt dysponuje licencjonowanymi plikami fontu. Rezerwa to Arial, Helvetica, sans-serif. Rozmiary stosuj w rem, a interlinię bez jednostki. Poniżej ekwiwalenty przy domyślnych 16 px.

| Rola | Telefon | Desktop | Grubość |
| --- | --- | --- | --- |
| Slogan marketingowy | 28 / 36 px | 44 / 48 px | 400 lub 700 |
| H1 procesu | 28 / 36 px | 36 / 44 px | 700 |
| Tytuł sekcji marketingowej | 28 / 36 px | 48 / 56 px | 400 lub 700 |
| Tytuł panelu | 24 / 32 px | 28 / 36 px | 700 |
| Tytuł karty i krótkie śródtytuły | 20 / 26 px | 20 / 26 px | 700–800 |
| Treść i pole | 16 / 24 px | 16 / 24 px | 400 |
| CTA | 16 / 24 px | 16 / 24 px | 600–700 |
| Metadane i pomoc | 14 / 20 px | 14 / 20 px | 400–600 |
| Drobny przypis | 12 / 18 px | 12 / 18 px | 400–700 |

Tekst ciągły ogranicz do ok. 65–72 znaków w wierszu. Zachowaj polskie znaki i naturalne zawijanie. Wyróżnienie w sloganie stosuj tylko przy wyraźnym akcentowaniu sensu całej frazy.

### Spacing scale

| Wartości | Rola |
| --- | --- |
| 4, 8 px | Ikona z etykietą, bliskie powiązania, odstęp w zwartej grupie |
| 12, 16 px | Odstęp między polami lub kartami, pomoc i odstęp po nagłówku |
| 24, 32 px | Padding panelu, odstęp przed grupą akcji i między blokami |
| 40, 48 px | Większe wnętrze panelu i odstępy sekcji na telefonie |
| 64, 80, 96 px | Rytm sekcji i oddech wokół hero na desktopie |

Padding panelu procesu 16 px przy najmniejszej szerokości, 24 px standardowo, do 32–40 px w rozbudowanym panelu desktopowym. Odstęp od etykiety do pola 8 px, między grupami pól 16 px, do głównej akcji 24–32 px.

### Layout system i responsive breakpoints

Kontener ma `max-width: 1280px` i boczne marginesy bezpieczeństwa 16 px na telefonie, 24 px na tablecie oraz 32 px na desktopie. W treściach wielokolumnowych użyj siatki 4/8/12 kolumn odpowiednio dla telefonu, tabletu i desktopu, z odstępami 16/24/24–32 px. Powtarzalne karty produktu mogą mieć własny układ pięciu równych kolumn, gdy mieszczą się bez ściskania etykiet. Ekrany procesu mają centralną kolumnę do 560 px. Szeroki hero marketingowy ma rząd do 1160 px z panelem ok. 440 px, odstępem od 32 px i płynną kolumną ilustracji.

| Szerokość | Proponowany układ |
| --- | --- |
| 320–479 px | Jedna kolumna, CTA na całą szerokość, pełne nazwy akcji. Wzór kadru i opis nad akcją. |
| 480–767 px | Zachowaj jedną kolumnę procesu. Dwie kolumny dla niezależnych kart, jeśli mieszczą treść i cele dotykowe. |
| 768–991 px | Siatka tabletowa, szersze marginesy, tytuły sekcji mogą rosnąć. Formularz przed kampanią. |
| 992–1279 px | Dwie kolumny hero marketingowego, gdy obie mają miejsce na treść. Na ekranie procesu ilustracja może towarzyszyć instrukcji, o ile zachowana jest kolejność czytania. |
| Od 1280 px | Szeroki kontener. W marketingu pełne rzędy skrótów i kart, w procesie zachowana czytelna szerokość tekstu. |

Schematy kolejności treści

```text
Marketing, szeroki ekran         Oględziny, telefon
[marka | szukaj | akcje]          [marka          pomoc]
[       slogan        ]          [krok 3 z 8 | postęp]
[zakładki]                       [lewy bok pojazdu]
[panel   | kampania   ]          [instrukcja i wzór kadru]
[skrót  skrót  skrót  ]          [Wykonaj zdjęcie]
```

### Border radius, borders i shadows

| Token | Wartość | Rola |
| --- | --- | --- |
| `radius-control` | 6 px | CTA, pole, select |
| `radius-tile` | 8 px | Karta oferty, zakładka, skrót |
| `radius-panel` | 16 px | Karta zadania i większa powierzchnia |
| `radius-pill` | 999 px | Kapsuła wyszukiwania i wskaźnik postępu |
| `border-width` | 1 px | Kontrolki i podziały |
| `shadow-none` | `none` | Pola, przyciski i większość sekcji |
| `shadow-card` | `0 12px 24px -16px rgba(0,0,0,.22)` | Karta produktu |
| `shadow-panel` | `0 16px 48px -12px rgba(0,0,0,.20)` | Wiodący panel zadania |
| `shadow-overlay` | `0 12px 40px rgba(0,0,0,.18)` | Menu i dialog |

### Animations and transitions

| Interakcja | Parametry i reakcja |
| --- | --- |
| Hover CTA, linku, kafla | 150 ms `ease-out` dla koloru, tła lub obramowania. CTA ciemnieje, link zyskuje podkreślenie, kafel przechodzi w lawendę. Bez zmiany geometrii. |
| Naciśnięcie | 100 ms, krótkie przyciemnienie tła. Focus pojawia się od razu i jest widoczny niezależnie od hover. |
| Zakładka, rozwinięcie, dialog | 200 ms `ease-out`. Wypełnienie lub kontur wskazują wybór. Dla panelu dopuszczalna krótka zmiana przezroczystości. |
| Ręczna nawigacja karuzeli | 250 ms `ease-out`. Strzałki lub przyciski stron pozostają dostępne. |
| Ograniczenie ruchu | Przy `prefers-reduced-motion: reduce` zmiana stanu jest natychmiastowa. Postęp pozostaje czytelny tekstowo. |

## Component Library

| Komponent | Anatomia i układ | Stany i zachowanie |
| --- | --- | --- |
| Nagłówek marketingowy | Opcjonalny pasek kontaktowy, marka, szukaj, pomoc i menu. Wyszukiwarka ma wysokość 56–64 px i kapsułę. Na telefonie kontrolki ikonowe z nazwami dostępnymi. | Menu rozwija się po aktywacji, strzałka sygnalizuje stan, Escape zamyka warstwę. Fokus wraca do elementu otwierającego. |
| Nagłówek procesu | Marka z lewej, kontekstowa pomoc z prawej, wysokość ok. 56–64 px. | Pomoc ma stałą nazwę i położenie między krokami. Przy 320 px etykiety mogą przejść do drugiego wiersza. |
| CTA główne | Biały tekst na fiolecie, promień 6 px, wysokość min. 48 px, w panelu 50–64 px, padding poziomy 16–24 px. | Spoczynek, hover, aktywacja, focus, niedostępny i praca w toku. Podczas oczekiwania zachowaj wymiar i pokaż opis stanu. |
| CTA drugorzędne i link | Lawenda z fioletem dla alternatywnej akcji. Podkreślony link w treści, zwłaszcza przy dokumentach. | Zmiana tła lub podkreślenia na hover i osobny obrys fokusu. Akcję i nawigację odróżnia semantyka. |
| Panel zadania | Biała karta z promieniem 16 px. Tytuł, instrukcja, pola lub podgląd oraz blok działań. | Długa treść powiększa panel. Błędy inline i podsumowanie pozostają w normalnym przepływie. |
| Zakładki produktu | Piktogram 40–64 px w kaflu 72–88 px, kontur 1 px, promień 8 px, zwięzła nazwa widoczna lub dostępna. | Wybrany stan ma dodatkowy kontur lub znacznik. Nawigacja strzałkami, jeden aktywny panel, bez poziomego przepełnienia całej strony. |
| Pole tekstowe, data, select | Etykieta, kontrolka 50–64 px, promień 6 px, tekst 16 px, padding poziomy 16 px. Ikona zajmuje zarezerwowane miejsce. | Spoczynek, focus, wartość, błąd, stan wyłączony i tylko do odczytu. Pomoc oraz format mają trwałą etykietę. |
| Akceptacja regulaminu | Checkbox z klikalną etykietą i osobnym linkiem do treści. Cel dotykowy grupy co najmniej 44 px. | Niezaznaczony, zaznaczony, focus i błąd z instrukcją. Link do dokumentu jest odrębną akcją. |
| Skrót obsługi i karta oferty | Skrót ma lawendowe tło i krótką etykietę. Karta oferty zawiera konturową ilustrację, nazwę i CTA na białej powierzchni. | Główna akcja ma własny focus. W grupie wyrównaj CTA, zostawiając tytułom miejsce na dwa wiersze. |
| Karta korzyści, opinii i artykułu | Korzyść to ikona, tytuł i jednozdaniowy opis. Opinia to cytat i podpis na lawendzie. Artykuł to tytuł, data i opcjonalne zdjęcie, opis w wariancie wyróżnionym. | Cytat i artykuł mogą rosnąć wraz z treścią. Na telefonie zdjęcie jest nad tekstem. |
| Karuzela | Lista kart, podpisane strzałki, opcjonalne wskaźniki pozycji. Na telefonie jedna karta na widok, na desktopie liczba wynikająca z miejsca. | Obsługa przyciskami i dotykiem, aktywny wskaźnik z nazwą, niedostępna strzałka na końcu zakresu. Wąski ekran może użyć zwykłej listy, jeżeli porównanie pozycji jest ważniejsze. |
| Postęp oględzin | Tekst „Krok 3 z 8” i dyskretny pasek 4–6 px. Poniżej nazwa aktualnego ujęcia. | Po zmianie kroku aktualizuj opis i kieruj fokus na tytuł. Komplet otrzymuje ikonę i zwięzłe potwierdzenie. |
| Wzór kadru i podgląd | Proporcja bazowa 4:3, promień 8 px. Wzór pokazuje kierunek i krawędzie ujęcia. Podgląd zdjęcia używa `object-fit: contain`, żeby można było ocenić cały kadr. | Przed zdjęciem instrukcja i akcja „Wykonaj zdjęcie”. Po zdjęciu podgląd oraz akcje „Zatwierdź zdjęcie” i „Powtórz”. Anulowanie powtórzenia zachowuje poprzedni podgląd. Licznik zatwierdzonych ujęć rośnie po zatwierdzeniu. |
| Komunikat i dialog | Ikona 20–24 px, tytuł i tekst na jasnej powierzchni. Dialog ma promień 16 px i wyraźne akcje. | Status ogłaszany czytnikowi. Dialog zarządza fokusem, zamyka się zgodnie z etykietą i przywraca fokus. |
| Stopka | Kontakt, potrzebne dokumenty i pogrupowane linki. W procesie krótka wersja z pomocą i informacjami dotyczącymi zadania. | Wąski ekran składa grupy pionowo. Jeśli grupy są zwijane, ich nagłówki pozostają dostępne z klawiatury. |

### Ilustracje i fotografie

Stosuj własne dwubarwne piktogramy. Kontur około 1,5–2 px przy siatce ikony 24 px, ciemny fiolet dla konstrukcji i fuksja dla detalu. Trzymaj wspólne grubości, zakończenia linii i skalę optyczną. Rysunki kroków pokazują perspektywę ujęcia i granicę obiektu. Dla VIN, licznika i dokumentów używaj fikcyjnych lub zanonimizowanych przykładów. W obszarach redakcyjnych dobieraj fotografie konkretnej sytuacji, z tematem w środku kadru i bez tekstu wtopionego w zdjęcie.

### Accessibility guidelines

- Cel jakości to WCAG 2.2 AA. Sprawdź kontrast tekstu 4,5:1, dla dużego tekstu 3:1, a dla istotnych granic kontrolek i wskaźników 3:1 względem sąsiedniego koloru. Utrzymaj minimum projektowe 44 × 44 px dla przycisków dotykowych. [WCAG 2.2](https://www.w3.org/TR/WCAG22/)
- Użyj widocznego obrysu fokusu o grubości 2 px i odsunięciu 3 px. Na ciemnej powierzchni zapewnij jasny obrys. Sprawdź, czy nagłówek lub przyklejony pasek akcji go nie zasłania.
- Zapewnij logiczne nagłówki, landmarki, etykiety pól i nazwę każdej kontrolki ikonowej. Dekoracje pomijaj w drzewie dostępności, a instrukcje kadru podaj również tekstem.
- Sygnalizuj stan ikoną, tekstem lub kształtem. Po błędzie zachowaj dane i pokaż, jak go poprawić. Bieżący krok, potwierdzenia i błędy mają zrozumiałe komunikaty dla czytnika ekranu.
- Testuj klawiaturę, zmianę orientacji, powiększenie tekstu do 200%, reflow przy 320 px i ograniczenie ruchu. Jeżeli pasek akcji jest przyklejony na telefonie, uwzględnij bezpieczny obszar ekranu i otwartą klawiaturę.

## Implementation Guidelines

1. Przeczytaj [brief projektu](brief.md) i [specyfikację](SPEC.md). Zachowaj opisany zakres funkcjonalny. Używaj dokumentu jako źródła tokenów, hierarchii i stanów.
2. Zacznij od ekranów wejścia i oględzin przy szerokości 390 px. Przenieś główną relację z referencji, czyli wyraźne zadanie w białym panelu, ilustrację pomagającą działać oraz fioletowe CTA. Wybierz wzór wymaganego ujęcia jako charakterystyczny element, z jasnym tłem i prostym nagłówkiem.
3. Zdefiniuj semantyczne tokeny dla kolorów, typografii, odstępów, promieni, cieni i czasów przejść. Stosuj je we wspólnych wariantach komponentów. Wymiary pól i kart traktuj jako minima lub szerokości maksymalne tam, gdzie treść może się rozrastać.
4. Ułóż treść zgodnie z kolejnością działania. Wstęp i akceptacja, aktualne ujęcie, wykonanie, sprawdzenie kadru, przejście do następnego ujęcia i potwierdzenie ukończenia. Pasek postępu odzwierciedla kolejność określoną w briefie.
5. Zaprojektuj stan początkowy, gotowość, podgląd, ponowienie i zakończenie. Sprawdź odmowę dostępu do aparatu i niedostępny aparat zgodnie z zakresem projektu. W komunikatach używaj tych samych nazw czynności co w przyciskach.
6. Zbuduj własną strukturę, style i ilustracje na podstawie opisanych zasad. Korzystaj z zatwierdzonych plików marki, jeśli są dostępne. Przed użyciem fontu lub zasobów kampanii ustal prawo do ich wykorzystania.
7. Zweryfikuj układ przy 320, 390, 768, 992 i 1440 px. Obejrzyj długie polskie etykiety, grupy CTA, podgląd zdjęcia, brak przepełnienia i zachowanie fokusu. Porównaj zwłaszcza hierarchię panelu, czytelność formularza i proporcje pustej przestrzeni.

## Design Consistency Rules

- Każdy ekran ma jeden główny cel i jedno wiodące CTA w danym obszarze. Powiązane akcje drugorzędne używają lawendy lub stylu linku.
- Nowe podstrony dziedziczą rodzinę fontu, skalę, znaczenia kolorów, oś wyrównania i rytm odstępów. Różnicuj układ odpowiednio do treści.
- Wybieraj promień zgodnie z rolą powierzchni. Głęboki cień zarezerwuj dla centralnego panelu, a podziały w jego wnętrzu buduj odstępem.
- Etykiety i komunikaty utrzymuj w trybie zdaniowym. Numeracja oznacza realny krok lub pozycję, a nie ozdobę.
- Powtarzalne ikony mają tę samą kreskę i optyczny rozmiar. Obszary aktywne, błędy i potwierdzenia zachowują wspólny wygląd i nazewnictwo.
- Na telefonie pomoc i działania dodatkowe pozostają po właściwej stronie hierarchii. Układ umożliwia przejście od tytułu do akcji w tej samej kolejności wzrokiem, dotykiem i klawiaturą.

## Anti-patterns

- Gradient na tle całego ekranu, fuksja w dużych blokach tekstu i kilka przycisków o tej samej dominującej wadze.
- Identyczne cienie i duże promienie na każdej powierzchni, kapsuły stosowane do wszystkich pól, zagnieżdżone karty bez funkcji.
- Drobne etykiety udające placeholder, akcje dostępne tylko przez hover, sygnalizowanie błędu wyłącznie kolorem.
- Sztuczne wyróżnianie pojedynczego słowa w każdym tytule, dekoracyjne nadtytuły, rozstrzelone wersaliki i numeracja sekcji bez kolejności.
- Generyczne grafiki i zdjęcia stockowe w miejscu precyzyjnej instrukcji kadrowania. Przycinanie podglądu zdjęcia używanego do oceny ujęcia.
- Animowanie wejścia każdej sekcji, automatyczna rotacja kart w procesie i przyklejone elementy zasłaniające pole, fokus lub główną akcję.
- Przenoszenie kampanii, rabatów, nawigacji sprzedażowej i czatu na ekran oględzin bez związku z zadaniem klienta.
