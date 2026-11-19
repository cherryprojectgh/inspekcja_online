# F04 · Zakończenie i odbiór ścieżki

**Status:** do zrobienia · **Priorytet:** MVP-1 · **Złożoność:** średnia → Średni, ponieważ karta używa istniejących reguł dostępu i zapisuje jeden stan końcowy.  
**Zależy od:** F03 · **Źródło:** DEC-1, DEC-3, DEC-5 oraz specyfikacja prototypu US6.

## Do przeczytania

[Specyfikacja, sekcje 3, 5–7 i 12](../specyfikacja.md), [DESIGN.md](../../DESIGN.md), [zasady pracy](../../AGENTS.md).

## Cel i zachowanie

Na E3 po zapisaniu ośmiu ujęć uczestnik wybiera „Zakończ”. Serwer weryfikuje ważność linku i komplet, po czym zapisuje zakończenie. E4 pojawia się po potwierdzeniu i wskazuje właściwy pojazd oraz zakończenie inspekcji. Ponowne otwarcie ważnego linku pokazuje E4 bez edycji. Po wygaśnięciu linku działa E5.

## Dane

Odczyt stanu sprawy i kompletu ujęć, zapis stanu zakończenia. Ponowienie tego samego zakończenia z ważnym linkiem zachowuje stan. Po zakończeniu nie można zmienić zdjęć.

## Kryteria akceptacji

- **F04-KA1 [test].** Serwer odrzuca zakończenie przy siedmiu zapisanych ujęciach. Przy ośmiu zapisuje zakończenie, a aplikacja pokazuje E4 dopiero po potwierdzeniu.
- **F04-KA2 [test].** Przy błędzie zapisu użytkownik może ponowić zakończenie. Utrata odpowiedzi po udanym zapisie nie tworzy drugiego zakończenia.
- **F04-KA3 [test].** Ponowne otwarcie ważnego linku pokazuje E4, a serwer odrzuca próby zmiany zdjęć. Po wygaśnięciu linku serwer odrzuca również odczyt (N2–N3).
- **F04-KA4 [ręcznie].** Na iPhonie z Safari i Samsungu z Chrome uczestnik otwiera link, akceptuje regulamin, robi trzy zdjęcia, zamyka przeglądarkę, wraca do 3/8, robi pięć pozostałych zdjęć, poprawia jedno i kończy inspekcję. Ponownie otwiera link i widzi E4.

## Błędy, ochrona danych i granice karty

Przy nieudanym zakończeniu ekran zachowuje komplet i umożliwia ponowienie. Używaj fikcyjnych spraw i rekwizytów, bez materiałów z rzeczywistych oględzin. Karta nie przekazuje zdjęć do panelu pracownika i nie uruchamia automatycznej oceny.

## Sprawdzenie ręczne

Wykonaj ścieżkę z F04-KA4. Zapisz wynik dla obu urządzeń. Osobno użyj sprawy, której termin mija podczas otwartej sesji, i sprawdź komunikat oraz brak dalszego dostępu.
