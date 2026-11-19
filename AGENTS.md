# Zasady pracy w projekcie Inspekcja online

- [Specyfikacja MVP](docs/specyfikacja.md) opisuje zakres, model danych, decyzje i reguły dostępu. [Karty](docs/funkcje/) podają kolejność i kryteria odbioru. Plan techniczny powstaje w `docs/plan.md`.
- [DESIGN.md](DESIGN.md) i [prototyp](prototyp.html) są odniesieniem dla wyglądu i przebiegu. Stosuj zatwierdzony zakres z dokumentacji MVP. Rozbieżności zgłaszaj z linkami do odpowiednich miejsc i wskaż, co blokują.
- Przed pracą sprawdź stan repozytorium i przeczytaj kartę oraz powiązaną część planu. Szanuj istniejące zmiany. Po pracy sprawdź kryteria i zaktualizuj stan funkcji w planie oraz README.
- W kodzie, testach i dokumentach używaj fikcyjnych spraw, przykładowych zdjęć i atrap sekretów. Dane dostępowe konfiguruj w środowisku. Nie odczytuj plików z sekretami, nie zapisuj pełnych linków do spraw, zdjęć ani sekretów w logach i repozytorium.
- Dostęp i ważność linku weryfikuj po stronie serwera. Utrzymuj prywatny dostęp do zdjęć i sprawdź, że link jednej sprawy nie udostępnia innej.
- Środowisko MVP jest testowe. Przejście na rzeczywiste sprawy wymaga decyzji właściciela. Firma właściciela nie akceptuje Supabase w produkcji.
