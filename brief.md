# Brief prototypu: zdjęcia pojazdu przed ubezpieczeniem

## 1. Problem

Przed przyjęciem samochodu do ubezpieczenia ubezpieczyciel chce obejrzeć pojazd, aby upewnić się, że jest sprawny. Klient musi umówić rzeczoznawcę, poczekać na oględziny, a następnie na przekazanie zdjęć ubezpieczycielowi. W tym zdarzeniu samodzielne wykonanie określonych zdjęć przez klienta ma zastąpić wizytę rzeczoznawcy.

## 2. Użytkownik

**Klient** chce ubezpieczyć samochód wymagający oględzin. Otwiera otrzymany link na swoim smartfonie i wykonuje zdjęcia zgodnie z instrukcjami aplikacji, bez instalowania oprogramowania. Ma 5 dni na wykonanie zdjęć.

**Pracownik ubezpieczyciela — kontekst pełnego procesu, poza prototypem:** generuje lub wysyła klientowi link, a po wykonaniu zdjęć przegląda je w aplikacji i decyduje o dalszych krokach w procesie.

W przyszłości AI będzie weryfikować, czy zdjęcia są prawidłowe. Jeśli wykryje rozbieżności, przekaże je pracownikowi, który podejmie decyzję o dalszych krokach w procesie. Ta weryfikacja przez AI pozostaje poza prototypem.

## 3. Wartość

Klient przechodzi przez wykonanie i przekazanie zdjęć bez umawiania rzeczoznawcy i oczekiwania na jego wizytę oraz przesłanie materiału. Instrukcje mają prowadzić go krok po kroku przez wymagane ujęcia.

Ubezpieczyciel ma ograniczyć koszty wysyłania rzeczoznawców oraz zwiększyć skalę wykonywania zdjęć przed przyjęciem samochodów do ubezpieczenia.

## 4. Zakres

Prototyp powstanie w tym folderze jako jeden plik HTML, bez serwera, bazy danych i logowania, na danych fikcyjnych. Obejmuje wyłącznie ścieżkę klienta: **klient otrzymuje link → otwiera aplikację → akceptuje regulamin → wykonuje osiem zdjęć**. Otrzymany link jest punktem wejścia do prototypu; jego generowanie i wysyłka nie są częścią tej ścieżki.

### Ekrany i kroki ścieżki

1. **Klient — wejście i regulamin.** Otwiera otrzymany link w przeglądarce telefonu, bez instalowania aplikacji, i akceptuje osadzony regulamin. Treści regulaminu nie podano w czacie.
2. **Klient — wykonywanie zdjęć.** Aplikacja prowadzi go krok po kroku, mówiąc lub pokazując, jakie zdjęcie wykonać. Ścieżka kończy się po wykonaniu kompletu ośmiu zdjęć. Wymagany zestaw obejmuje:
   - przód pojazdu;
   - tył pojazdu;
   - lewy bok pojazdu;
   - prawy bok pojazdu;
   - licznik;
   - VIN;
   - pierwsza strona dowodu rejestracyjnego;
   - druga strona dowodu rejestracyjnego.

W pełnym procesie klient ma 5 dni na wykonanie zdjęć i powinien otrzymywać powiadomienia, jeśli jeszcze ich nie wykonał. Ten prototyp służy przejściu przez wykonywanie zdjęć podczas jednej sesji; nie obejmuje obsługi powrotu do sprawy przez 5 dni ani automatycznych przypomnień.

### Poza prototypem

- Serwer, baza danych i logowanie.
- Generowanie i wysyłka linku do klienta.
- Przesyłanie zdjęć do ubezpieczyciela, widok pracownika oraz podejmowanie przez niego decyzji o dalszych krokach.
- Trwałe przechowywanie zdjęć i stanu sprawy przez 5 dni oraz automatyczne powiadomienia przypominające.
- Automatyczna weryfikacja prawidłowości zdjęć przez AI i przekazywanie wykrytych rozbieżności pracownikowi — to przyszły etap aplikacji.

## 5. Co testujemy

**Założenie o użyteczności:** prowadzenie krok po kroku wystarcza, aby klient samodzielnie wykonał osiem wymaganych zdjęć. **Warunek niepotwierdzenia:** podczas testu klient potrzebuje dodatkowych wyjaśnień, jakie ujęcie wykonać lub jak przejść dalej, albo kończy ścieżkę z niekompletnym zestawem lub zdjęciem niezgodnym z instrukcją. Zgodność zdjęć ocenia tester, ponieważ automatyczna weryfikacja jest poza zakresem.

**Założenie o technologii:** klient może otworzyć link i wykonać wymagane zdjęcia w przeglądarce smartfona bez instalowania aplikacji. Docelowa deklaracja obejmuje wszystkie modele smartfonów. **Warunek niepotwierdzenia:** na którymkolwiek testowanym smartfonie nie można otworzyć prototypu lub wykonać i wykorzystać w nim zdjęć bez instalacji. Przejście testu na wybranych urządzeniach nie potwierdza działania na wszystkich modelach; listy urządzeń i przeglądarek nie określono.
