---
version: alpha
name: Inspekcja online
description: "System wizualny prototypu, który prowadzi klienta przez wykonanie ośmiu zdjęć pojazdu przed ubezpieczeniem."
colors:
  surface: "#ffffff"
  primary: "#a50f82"
  primary-dark: "#850b69"
  heading: "#501e82"
  accent: "#a50f82"
  ink: "#3e3e3e"
  muted: "#70677a"
  line: "#e7dfec"
  paper: "#faf8fc"
  soft: "#f2ebfa"
  input-border: "#d7c9e1"
  progress-track: "#e8ddf0"
  illustration-bg: "#f5effa"
  terms-bg: "#faf7fc"
  camera-bg: "#241235"
  error: "#95352e"
  error-surface: "#fff1ee"
  disabled-surface: "#eeeaf0"
  disabled-text: "#68616e"
  card-shadow: "#501e8205"
  button-shadow: "#a50f8212"
  button-hover-shadow: "#a50f8225"
typography:
  body:
    fontFamily: "Plus Jakarta Sans, Arial, Helvetica, sans-serif"
    fontSize: "1rem"
    fontWeight: 400
    lineHeight: 1.6
  headline:
    fontSize: "1.625rem"
    fontWeight: 700
    lineHeight: 1.2
    letterSpacing: "-0.03em"
  headline-tablet:
    fontSize: "1.875rem"
    fontWeight: 700
    lineHeight: 1.2
    letterSpacing: "-0.03em"
  title:
    fontSize: "1.125rem"
    fontWeight: 700
    lineHeight: 1.3
  small:
    fontSize: "0.875rem"
    lineHeight: 1.42857
  button:
    fontWeight: 600
rounded:
  control: "6px"
  tile: "9px"
  illustration: "10px"
  panel: "14px"
  pill: "999px"
spacing:
  xs: "4px"
  sm: "8px"
  md: "12px"
  lg: "16px"
  xl: "24px"
  xxl: "32px"
  panel-mobile: "22px"
  panel-tablet: "28px"
components:
  button-primary:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.surface}"
    typography: "{typography.button}"
    rounded: "{rounded.control}"
    padding: "8px 16px"
  button-primary-hover:
    backgroundColor: "{colors.primary-dark}"
  button-secondary:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.heading}"
    typography: "{typography.button}"
    rounded: "{rounded.control}"
    padding: "8px 16px"
  button-disabled:
    backgroundColor: "{colors.disabled-surface}"
    textColor: "{colors.disabled-text}"
  inspection-card:
    backgroundColor: "{colors.surface}"
    rounded: "{rounded.panel}"
    padding: "{spacing.panel-mobile}"
  photo-thumbnail:
    backgroundColor: "{colors.surface}"
    rounded: "{rounded.tile}"
  error-box:
    backgroundColor: "{colors.error-surface}"
    textColor: "{colors.error}"
    rounded: "{rounded.tile}"
    padding: "{spacing.md}"
---

# Inspekcja online

## Overview

Inspekcja online pomaga klientowi samodzielnie sfotografować pojazd przed ubezpieczeniem. Klient otwiera sprawę na telefonie, akceptuje regulamin, wykonuje po jednym ujęciu w każdym kroku, przegląda komplet i kończy demonstrację. Biała karta skupia uwagę na bieżącym zadaniu. Dane pojazdu i licznik pozwalają sprawdzić, czy klient jest we właściwej sprawie i ile zdjęć pozostało.

## Colors

Prototyp korzysta z jednego jasnego motywu: fioletowe nagłówki i elementy marki, magenta akcji, białe karty i lawendowe tła. `paper` jest tłem strony, `surface` tłem kart, `soft` tłem stopki i wyróżnień, a `line` oddziela powierzchnie. `ink` służy do tekstu podstawowego, `muted` do objaśnień. `primary` z białym tekstem wyróżnia główną akcję, `primary-dark` to jej kolor po najechaniu, a `accent` pojawia się w logo i gradiencie postępu. Błąd ma tekst na jasnoczerwonym tle, a przycisk nieaktywny używa osobnej, stonowanej palety.

## Typography

Plus Jakarta Sans jest osadzony w pliku HTML w wagach 400, 600 i 700. Tekst podstawowy ma 16 px przy domyślnym rozmiarze przeglądarki; instrukcje i metadane korzystają z krótkich akapitów i opisów. Nagłówek ekranu ma 26 px na telefonie i 30 px od 600 px, a tytuł sekcji 18 px. Krótkie etykiety przycisków mają wagę 600.

## Layout

| Szerokość ekranu | Układ ścieżki | Margines boczny ramy / padding karty |
| --- | --- | --- |
| Do 374 px | Jedna kolumna, galeria w jednej kolumnie | 16 / 16 px |
| 375–599 px | Jedna kolumna, galeria w dwóch kolumnach | 16 / 22 px |
| Od 600 px | Jedna kolumna, galeria w dwóch kolumnach, akcje zdjęcia obok siebie | 24 / 28 px |

Interfejs jest przeznaczony dla telefonu i tabletu, w pionie i poziomie. Rama strony i obszar ścieżki mają maksymalnie 720 px. Większy ekran zachowuje wyśrodkowany układ tabletowy. Dane pojazdu i pasek postępu są nad kartą, bez bocznej kolumny. Na telefonie ekran zdjęcia pokazuje skrócony blok danych pojazdu. Zatwierdzone ujęcia są dostępne z rozwijanej listy pod kartą zdjęcia i z galerii podsumowania.

Akcje wykonania, powtórzenia i zatwierdzenia zdjęcia są przypięte do dolnej krawędzi. Od 600 px oraz na ekranach poziomych o szerokości co najmniej 480 px i wysokości do 500 px główna i drugorzędna akcja są obok siebie. Wysokość paska jest mierzona po zmianie treści i rozmiaru; odpowiadający jej zapas przewijania pozwala odsłonić treść i nawigację. Na krótkich ekranach instrukcję i podgląd można przewijać, pozostawiając akcje dostępne. Uwzględnij bezpieczne obszary ekranu i zachowaj możliwość powiększania strony.

## Elevation & Depth

Główna karta ma obrys 1 px i lekki cień `0 5px 24px var(--card-shadow)`. Cień przycisku głównego rośnie po najechaniu; przycisk drugorzędny pozostaje płaski. Dialog pomocy używa cienia `0 12px 40px rgba(0,0,0,.18)` i półprzezroczystego przyciemnienia tła, by oddzielić pomoc od bieżącego kroku.

## Shapes

Karta i dialog mają promień 14 px, przyciski 6 px, przykłady kadru 10 px, a podglądy, miniatury i panele rozwijane 9 px. Kółka kroków mają 25 × 25 px. Cienkie narożniki kadru łączą przykłady zdjęć z motywem logo.

## Components

### Nagłówek, stopka i pomoc

Biały nagłówek mieści osadzone logo, nazwę „Zdalna inspekcja pojazdu” i przycisk „Pomoc”. Ma co najmniej 72 px wysokości, powiększanej w razie potrzeby przez treść lub bezpieczny obszar ekranu. Na małym telefonie nazwa zawija się, a przycisk pomocy pozostaje w jednej linii. Stopka na lawendowym tle oznacza stronę jako „Wersja demonstracyjna”. Dialog pomocy objaśnia dostęp do aparatu i wskazuje możliwość użycia zdjęcia demonstracyjnego.

### Akcje, regulamin i postęp

Główna akcja ma jednolite wypełnienie, drugorzędna białe tło i kontur. Obie mają co najmniej 50 px wysokości. Akcje tekstowe zachowują pole dotyku co najmniej 44 × 44 px. Regulamin rozwija się w karcie przygotowania; „Rozpocznij zdjęcia” staje się aktywne po zaznaczeniu akceptacji. Zachowuj widoczny fokus klawiatury. Przejścia trwają zwykle 150 ms, a odsłonięcie treści 200 ms; ustawienie ograniczonego ruchu wyłącza animacje i przejścia.

Pasek postępu ma 5 px wysokości i towarzyszy mu tekstowy licznik zatwierdzonych zdjęć. W liście kroków aktywne ujęcie ma wypełnione kółko i oznaczenie `aria-current="step"`; gotowe ujęcie ma znak zatwierdzenia. Samo wyświetlenie zdjęcia w podglądzie nie zwiększa licznika.

### Ujęcie, galeria i zakończenie

Każdy krok pokazuje nazwę, instrukcję i przykład kadru. Kolejność: przód, tył, lewy bok, prawy bok, licznik, VIN, pierwsza i druga strona dowodu rejestracyjnego. Przykłady korzystają z osadzonych materiałów Fotoinspekcji oraz ilustracji VIN użytej w prototypie. Lustrzane odbicie stosuje się do przykładu i zdjęcia demonstracyjnego prawego boku.

„Wykonaj zdjęcie” otwiera kontrolkę wyboru obrazu z prośbą o tylny aparat. Klient sprawdza podgląd, może wybrać „Powtórz” albo „Zatwierdź zdjęcie”. Podgląd i miniatury mają bazowe proporcje 4:3 i pokazują cały obraz dzięki `object-fit: contain`. Zdjęcia demonstracyjne mają własną etykietę.

Podsumowanie pokazuje dane pojazdu i osiem podpisanych miniatur. Wybranie miniatury umożliwia poprawienie konkretnego ujęcia. Po „Zakończ” karta z ikoną zatwierdzenia potwierdza ukończenie demonstracji. Zdjęcia i postęp pozostają w pamięci bieżącej karty przeglądarki.

## Do's and Don'ts

- Prowadź użytkownika krótkimi instrukcjami po polsku i jedną wyraźną akcją główną na ekran.
- Pokazuj postęp i status również tekstem lub symbolem. Zostaw czytelny fokus i wygodne cele dotykowe.
- Pokazuj cały kadr; klient musi móc ocenić, czy na zdjęciu mieszczą się wymagane elementy.
- Rozróżniaj zdjęcie robocze, zatwierdzone i demonstracyjne. Nie obiecuj zapisu po zamknięciu karty ani wysyłki do ubezpieczyciela.
- Zasady zapisu, wznowienia i wygaśnięcia linku traktuj jako wymagania MVP ze [specyfikacji](docs/specyfikacja.md).
