# F00 · Fundament i środowisko testowe

**Status:** do zrobienia · **Priorytet:** MVP-1 · **Złożoność:** wysoka → Wysoki, ze względu na usługi zewnętrzne i dostęp do danych.  
**Zależy od:** planu technicznego · **Źródło:** DEC-1, DEC-4, A2.

## Do przeczytania

[Specyfikacja, sekcje 6–9](../specyfikacja.md), [zasady pracy](../../AGENTS.md), [DESIGN.md](../../DESIGN.md).

## Cel i zachowanie

Przygotuj aplikację, którą da się uruchomić lokalnie oraz otworzyć przez HTTPS w środowisku testowym. Przygotuj schemat bazy, prywatny magazyn zdjęć, konfigurację ze zmiennymi środowiskowymi, powtarzalne dane startowe i polecenie uruchamiające testy. Opisz uruchomienie oraz sposób odtworzenia spraw w README.

Przed integracją przeprowadź krótką próbę aparatu przez HTTPS na iPhonie i Samsungu. Sprawdź uzyskanie podglądu, zrobienie zdjęcia i zwolnienie aparatu po wyjściu z próby. Zapisz wyniki według urządzenia i przeglądarki. Rozwiąż niezgodność albo zgłoś ją przed rozpoczęciem integracji zapisu.

## Dane i dostęp

Przygotuj co najmniej dwie odrębne fikcyjne sprawy z różnymi linkami i możliwość przygotowania sprawy z upłyniętym terminem. Używaj plików testowych i przykładowych nazw zmiennych. Dane logowania oraz aktualne sekrety przechowuj w konfiguracji środowiska. Magazyn zdjęć ma być prywatny.

## Kryteria akceptacji

- **F00-KA1 [ręcznie].** Aplikacja uruchamia się zgodnie z instrukcją, a środowisko prób udostępnia stronę przez HTTPS na obu telefonach.
- **F00-KA2 [test].** Ponowne przygotowanie danych startowych daje oczekiwane fikcyjne sprawy. Magazyn odrzuca publiczny odczyt testowego pliku.
- **F00-KA3 [ręcznie].** Repozytorium zawiera wzór konfiguracji i ignoruje pliki z sekretami. Testy można uruchomić jednym udokumentowanym poleceniem.
- **F00-KA4 [ręcznie].** Próba aparatu ma zapisany wynik dla Safari na iPhonie i Chrome na Samsungu, z wersjami systemów i przeglądarek.

## Błędy, ochrona danych i granice karty

Brak konfiguracji ma dać czytelny błąd bez wartości sekretów. Gdy środowisko jest niedostępne, zgłoś wymaganą konfigurację i zachowaj możliwość wykonania prób lokalnych. Karta nie obejmuje pełnej obsługi linku, zapisów zdjęć, produkcji ani dostępu do realnych spraw.

## Sprawdzenie ręczne

Uruchom lokalnie według README, przygotuj fikcyjne sprawy, otwórz próbę aparatu na obu telefonach i powtórz ją po odmowie uprawnienia.
