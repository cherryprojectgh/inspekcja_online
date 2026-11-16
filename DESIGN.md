# System wizualny inspekcji online

Oprawa ścieżki klienta pochodzi z lokalnego projektu Fotoinspekcja (`C:\Projekty\zip`). Prototyp przenosi znak samochodu w kadrze, geometrię nagłówka, fioletową paletę, panel postępu i ilustracje.

## Kolorystyka

| Rola | Wartość |
| --- | --- |
| Nagłówki, znak pojazdu | `#501e82` |
| Główny przycisk | `#a50f82` |
| Główny przycisk po najechaniu | `#850b69` |
| Akcent kadru | `#a50f82` |
| Tło strony | `#faf8fc` |
| Tło stopki i łagodne wypełnienia | `#f2ebfa` |
| Tło ilustracji | `#f5effa` |
| Kontur karty | `#e7dfec` |

Interfejs używa fontu Plus Jakarta Sans w odmianach 400, 600 i 700. Przyciski mają promień 6 px, karty 14 px. Biała karta zadania ma cienki kontur. Główna akcja ma jednolite wypełnienie, a drugorzędna białe tło i kontur.

## Układ

Od 761 px dane pojazdu, pasek postępu i lista ujęć znajdują się obok karty bieżącego zadania. Numer wyróżnia aktywny krok, a znak zatwierdzenia oznacza gotowe ujęcia. Na telefonie dane pojazdu i postęp są nad kartą. Zatwierdzone ujęcia można otworzyć z rozwijanej listy pod kartą zdjęcia lub z galerii podsumowania.

## Materiały

Logo i favicon przeniesiono z Fotoinspekcji. Ilustracje przygotowania, przodu, tyłu, boków i licznika pochodzą z `static/illustrations` i są osadzone jako WebP. Prawy bok korzysta z lustrzanego odbicia ilustracji lewego. Wzory obu stron dowodu pochodzą z szablonu `templates/illustration.html`. Ujęcie VIN korzysta z ilustracji dostarczonej w tym prototypie.

Arkusz stylów, skrypty, fonty i grafiki są osadzone w [prototyp.html](prototyp.html). Licencja SIL OFL dla fontu jest w nagłówku pliku.
