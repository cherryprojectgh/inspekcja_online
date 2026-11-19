# Inspekcja online

Aplikacja ma prowadzić osobę wykonującą oględziny ubezpieczeniowe przez osiem zdjęć pojazdu w przeglądarce telefonu. Pierwsza działająca wersja ma obsługiwać przygotowane fikcyjne sprawy i pozwolić wznowić przerwane oględziny.

Klikalny [prototyp](index.html) pokazuje ścieżkę klienta. Otwórz plik w przeglądarce, by przejść demonstrację. Sposób uruchomienia działającego MVP zostanie opisany po przygotowaniu fundamentu.

Prototyp jest dostosowany do telefonów i tabletów: jedna kolumna do 720 px, sterowanie dotykowe i stale dostępne akcje zdjęcia przy dolnej krawędzi. Na większym ekranie zachowuje układ tabletowy. Weryfikację układu opisano w [planie](docs/plan.md#sprawdzenie-układu-prototypu--19-listopada-2026).

Plik wejściowy to `index.html`, dzięki czemu serwer statyczny otwiera prototyp pod adresem głównym strony.

Zakres ustalono w [specyfikacji MVP](docs/specyfikacja.md). Uwagi uczestników i plan ponownego testu są we [wnioskach z testów](docs/wnioski-z-testow.md).

## Stan funkcji

| Funkcja | Stan |
| --- | --- |
| [F00 · Fundament i środowisko testowe](docs/funkcje/F00-fundament.md) | W trakcie. Ekran próby aparatu gotowy lokalnie. |
| [F01 · Link i regulamin](docs/funkcje/F01-link-i-regulamin.md) | Zaplanowana |
| [F02 · Aparat i podgląd ujęcia](docs/funkcje/F02-aparat-i-podglad.md) | Zaplanowana |
| [F03 · Zapis, wznowienie i poprawa zdjęć](docs/funkcje/F03-zapis-i-wznowienie.md) | Zaplanowana |
| [F04 · Zakończenie i odbiór ścieżki](docs/funkcje/F04-zakonczenie.md) | Zaplanowana |

Kolejność budowy i harmonogram opisuje [plan techniczny](docs/plan.md). Plik [ekranu próbnego](proba-aparatu/index.html) jest gotowy do udostępnienia przez HTTPS i sprawdzenia na iPhonie z Safari oraz Samsungu z Chrome.
