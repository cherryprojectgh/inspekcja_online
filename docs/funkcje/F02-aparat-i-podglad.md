# F02 · Aparat i podgląd ujęcia

**Status:** do zrobienia · **Priorytet:** MVP-1 · **Złożoność:** wysoka → Wysoki, ze względu na obsługę aparatu i różnice między telefonami.  
**Zależy od:** F00, F01 · **Źródło:** DEC-2, DEC-3, W1, W2 oraz specyfikacja prototypu US2.

## Do przeczytania

[Specyfikacja, sekcje 3, 5, 7 i 9](../specyfikacja.md), [prototyp](../../index.html), [DESIGN.md](../../DESIGN.md), [wyniki testów](../wnioski-z-testow.md), [zasady pracy](../../AGENTS.md).

## Cel i zachowanie

Na E2 uczestnik widzi rodzaj ujęcia, instrukcję, przykład kadru, licznik zatwierdzonych ujęć oraz przycisk „Zrób zdjęcie” bez konieczności przewijania. Ilustracja VIN-u pokazuje miejsce przy szybie używane w teście.

Przycisk uruchamia aparat. Po zrobieniu zdjęcia aplikacja od razu przypisuje podgląd do bieżącego ujęcia. „Powtórz” pozwala zrobić nowe zdjęcie. Anulowanie ponowienia zachowuje poprzedni podgląd. „Zatwierdź zdjęcie” przekazuje ujęcie do zapisu realizowanego przez F03. Aplikacja zwalnia aparat po opuszczeniu kroku lub zakończeniu użycia.

## Dane

Typ ujęcia, aktualny postęp oraz roboczy obraz z aparatu. Obraz jest tymczasowy do zatwierdzenia. Karta nie zapisuje pliku do magazynu.

## Kryteria akceptacji

- **F02-KA1 [ręcznie].** Na obu fizycznych telefonach uczestnik otwiera aparat, robi zdjęcie i widzi je w podglądzie właściwego ujęcia. W interfejsie aparatu i aplikacji nie ma wyboru wcześniejszego zdjęcia z galerii ani pliku (N5).
- **F02-KA2 [ręcznie].** „Powtórz” wykonuje nowe zdjęcie, a anulowane ponowienie zachowuje poprzedni podgląd.
- **F02-KA3 [ręcznie].** Odmowa dostępu do aparatu pokazuje wskazówkę i umożliwia ponowienie po zmianie uprawnień. Licznik się nie zmienia i nie pojawia się wybór pliku.
- **F02-KA4 [ręcznie].** Przycisk „Zrób zdjęcie” jest widoczny bez przewijania na obu testowych telefonach. Uczestnik korzystający z instrukcji VIN dostaje możliwość odszukania paska bez podpowiedzi testera. Wynik odnotowujemy osobno.

## Błędy, ochrona danych i granice karty

Gdy aparat jest niedostępny, pokaż instrukcję i opcję ponowienia. Nie zapisuj podglądu w logach. F03 obsługuje potwierdzenie zapisu, ponowienie wysyłki i przywracanie postępu.

## Sprawdzenie ręczne

Na iPhonie i Samsungu przejdź krok VIN, zrób zdjęcie, anuluj jedną próbę powtórzenia i zrób nowe zdjęcie. Następnie odmów uprawnienia i przejdź instrukcję ponowienia.
