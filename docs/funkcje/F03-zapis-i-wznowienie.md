# F03 · Zapis, wznowienie i poprawa zdjęć

**Status:** do zrobienia · **Priorytet:** MVP-1 · **Złożoność:** wysoka → Wysoki, ze względu na prywatny magazyn, reguły dostępu i ponawianie zapisów.  
**Zależy od:** F01, F02 · **Źródło:** DEC-1, DEC-2, DEC-5 oraz specyfikacja prototypu US4 i US5.

## Do przeczytania

[Specyfikacja, sekcje 3 i 5–9](../specyfikacja.md), [DESIGN.md](../../DESIGN.md), [zasady pracy](../../AGENTS.md).

## Cel i zachowanie

Po zatwierdzeniu aplikacja zapisuje zdjęcie ukończonego ujęcia w danej sprawie. Do czasu potwierdzenia widoczny jest stan zapisu. Potwierdzenie aktualizuje licznik i przechodzi do kolejnego kroku. Osiem zatwierdzonych ujęć otwiera E3 z podpisanymi miniaturami. Wybór miniatury pozwala zrobić i zatwierdzić nowe zdjęcie w tym samym kroku, a potem wrócić do E3.

Po powrocie z ważnego linku aplikacja odczytuje akceptację i zapisane ujęcia. Kieruje do pierwszego brakującego ujęcia lub E3, gdy komplet już zapisano. Bieżący podgląd bez zatwierdzenia nie jest częścią zapisanego postępu.

## Dane

Serwer wiąże jedno aktywne zdjęcie z parą sprawa–typ ujęcia. Przed odczytem pliku sprawdza ważność i przypisanie linku. Przed zapisem sprawdza także akceptację regulaminu i stan otwarty. Zdjęcia są dostępne przez aplikację i prywatny magazyn.

## Kryteria akceptacji

- **F03-KA1 [test i ręcznie].** Zatwierdź trzy ujęcia, zamknij przeglądarkę i otwórz ten sam link. Aplikacja pokazuje 3/8 i czwarte ujęcie. Po zapisaniu ośmiu wraca prosto do podsumowania.
- **F03-KA2 [test].** Ponowienie po błędzie sieci lub utracie potwierdzenia nie tworzy drugiego ujęcia i nie zwiększa licznika ponownie.
- **F03-KA3 [test].** Nieudana podmiana zachowuje poprzednie zdjęcie. Udana zmienia tylko wskazane ujęcie. Stan zapisanych danych pozostaje spójny przy ponowieniach.
- **F03-KA4 [test].** Serwer odrzuca zapis bez akceptacji, po zakończeniu lub po wygaśnięciu. Po wygaśnięciu i z obcego linku nie można pobrać zdjęcia (N1–N4).

## Błędy, ochrona danych i granice karty

Awaria zapisu nie zwiększa postępu. Aplikacja zachowuje podgląd na czas ponowienia w otwartej sesji. Błędy nie ujawniają ścieżek plików ani sekretów. Karta nie zmienia stanu na zakończony.

## Sprawdzenie ręczne

Użyj jednej sprawy do testu wznowienia i drugiej do próby odrzuconego dostępu. Przerwij połączenie przy zatwierdzaniu i sprawdź ponowienie po jego odzyskaniu. Z podsumowania popraw jedno zdjęcie.
