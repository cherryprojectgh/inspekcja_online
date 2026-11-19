# F01 · Link i regulamin

**Status:** do zrobienia · **Priorytet:** MVP-1 · **Złożoność:** wysoka → Wysoki, ponieważ karta wprowadza reguły dostępu do spraw.  
**Zależy od:** F00 · **Źródło:** DEC-1, DEC-5, A3, specyfikacja prototypu US1 i US5.

## Do przeczytania

[Specyfikacja, sekcje 4–7](../specyfikacja.md), [prototyp](../../prototyp.html), [DESIGN.md](../../DESIGN.md), [zasady pracy](../../AGENTS.md).

## Cel i zachowanie

Osoba z indywidualnym linkiem otwiera przypisaną fikcyjną sprawę i na E1 widzi dane pojazdu, termin, listę wymaganych ujęć i regulamin testowy. „Rozpocznij zdjęcia” działa po zaznaczeniu akceptacji. Po potwierdzonym zapisie uczestnik przechodzi do E2. Ponowne otwarcie ważnego linku zachowuje akceptację. Karty F03 i F04 wykorzystują dane zwrócone przy otwieraniu sprawy, aby przywrócić właściwy ekran.

Serwer egzekwuje dostęp przy każdym odczycie i zapisie. Link kieruje do jednej sprawy i wygasa po pięciu dniach od zlecenia. Dane pojazdu i zdjęcia pozostają niedostępne z nieważnego linku. Przy upływie terminu w trwającej sesji następna próba odczytu lub zapisu przechodzi na E5.

## Dane

Odczyt: przypisanie linku, dane pojazdu, termin, akceptacja i stan sprawy. Zapis: akceptacja zaakceptowanego regulaminu. Ponowienie akceptacji zachowuje istniejący stan.

## Kryteria akceptacji

- **F01-KA1 [test].** Link do TEST-001 otwiera tylko TEST-001. Próba dostępu do TEST-002 tym linkiem nie ujawnia danych sprawy ani zdjęć (N1; odczyt plików sprawdzi też F03).
- **F01-KA2 [test].** Po upływie terminu odczyt i zapis zostają odrzucone także w otwartej wcześniej sesji (N2).
- **F01-KA3 [ręcznie i test].** Bez akceptacji nie można zacząć zdjęć. Po udanym zapisie i ponownym otwarciu linku użytkownik nie akceptuje regulaminu drugi raz.
- **F01-KA4 [ręcznie].** Przy błędzie zapisu akceptacji uczestnik widzi komunikat i może ponowić próbę.

## Błędy, ochrona danych i granice karty

E5 pokazuje brak dostępu bez ujawniania danych sprawy. Nie zapisuj pełnych linków w logach. Karta nie obejmuje automatycznego tworzenia i wysyłki linków ani dodatkowego logowania.

## Sprawdzenie ręczne

Otwórz dwie fikcyjne sprawy i link wygasły. W jednej sprawie zaakceptuj regulamin, zamknij przeglądarkę i otwórz ponownie ten sam link.
