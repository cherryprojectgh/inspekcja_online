# SPEC.md — Inspekcja online

## 1. Aplikacja w jednym zdaniu

"Inspekcja online" prowadzi klienta krok po kroku przez proces wykonania ośmiu zdjęć pojazdu wymaganych do zawarcia umowy ubezpieczenia.

## 2. Kontekst użytkownika i ograniczenia

- Jeżeli Ubezpieczyciel uzna, że przed zawarciem umowy ubezpieczenia konieczne jest przeprowadzenie oględzin pojazdu, klient musi oczekiwać na kontakt ze strony rzeczoznawcy w celu ustalenia terminu oględzin. Celem oględzin jest zwerfikwowanie, czy samochód nie jest uszkodzony oraz czy deklarowane dane (np. przebieg pojazdu, numr VIN) są zgodne ze stanem faktycznym. Po przeprowadzeniu oględzin rzeczoznawca przekazuje dokumentację fotograficzną Ubezpieczycielowi, który na jej podstawie podejmuje decyzję o dalszych krokach w procesie zawierania umowy ubezpieczenia.
- Rzeczoznawca ma 24 godziny na kontakt z klientem oraz później 24 na odesłanie zdjęć wraz z protokołem. Średni czas procesu od momentu zlecenia oględzin do uzyskania wyniku to ok 3-4 dni.
- Ubezpieczyciel ma ograniczoną skalę wykonywania oględzin przed ubezpieczeniem samochodu - zasięg to cała Polska, ograniczona liczba rzeczoznawców.
- W docelowym procesie system automatycznie generuje linka i wysyła do Klienta. Po odesłaniu zdjęć system automatycznie analiuzje czy zdjęcia zawierają elementy wymagające dalszej weryfikacji (np. samochód jest uszkodzony, brak wszystkich stron pojazdu, niezgodność przebiegu z deklarowanym itp).
- Dzięki aplikacji Klient może szybko wykonać 8 prostych zdjęć i ubezpieczyć samochód bez konieczności oczekiwania i umawiania się z rzeczoznawcą.
- Dzięki aplikacji Ubezpieczyciel ogranicza koszty (rzecznzawca, zespół obsługujący proces) oraz zwiększa skale działania procesu.

### Użytkownicy i warunki korzystania

- **Kto wykonuje zdjęcia.** Z założenia zdjęcia wykonuje osoba zawierająca umowę ubezpieczenia. W praktyce może je wykonać osoba, której numer telefonu poda kupujący ubezpieczenie.
- **Miejsce i łączność.** Zdjęcia będą najczęściej wykonywane na parkingach. Dokładna lokalizacja osoby wykonującej zdjęcia i jakość połączenia w tym miejscu są nieznane.
- **Urządzenia i przeglądarki.** Docelowo klient korzysta z aplikacji na smartfonie z Androidem lub iOS, bez instalacji. Zakres testów prototypu obejmie uzgodnioną listę urządzeń i przeglądarek (Chrome, Edge, Firefox i Safari, zależnie od urządzenia). Wynik tych testów nie potwierdza zgodności ze wszystkimi modelami.
- **Termin docelowy.** Link wygasa po pięciu dniach od zlecenia oględzin. Po tym czasie nie można otworzyć sprawy ani dokończyć rozpoczętych oględzin. Prototyp pokazuje przykładowy termin i nie egzekwuje wygaśnięcia linku.
- **Dostęp docelowy.** Osoba, która otrzymała ważny link, może otworzyć sprawę i wykonać zdjęcia bez dodatkowego potwierdzenia kodem SMS. Prototyp otwiera fikcyjną sprawę.

## 3. Zakres

| Obszar | Wymagania prototypu | Opcjonalnie w prototypie |
|---|---|---|
| Start | Otwarcie fikcyjnej sprawy w przeglądarce telefonu bez instalacji. Przykładowy regulamin i obowiązkowa akceptacja przed rozpoczęciem zdjęć. | Spersonalizowany komunikat powitalny. |
| Zdjęcia | Instrukcja i przykład kadru dla każdego z ośmiu ujęć. Wykonanie zdjęcia aparatem telefonu, podgląd, powtórzenie i zatwierdzenie. | Przykładowe zdjęcia do demonstracji bez aparatu; obsługa aparatu bezpośrednio na ekranie aplikacji. |
| Zakończenie | Przegląd ośmiu ujęć, możliwość poprawienia pojedynczego zdjęcia i potwierdzenie zakończenia demonstracji. | — |

**Otwarte wymaganie: blokada galerii.** Założenie dla oględzin jest takie, że każde zdjęcie powstaje aparatem podczas sesji. Obecny prototyp prosi przeglądarkę o otwarcie aparatu, ale nie sprawdza pochodzenia zdjęcia. Możliwość wybrania zdjęcia z galerii trzeba sprawdzić na urządzeniach testowych. Zdjęcia demonstracyjne służą do sprawdzenia przebiegu ścieżki i nie zaliczają testu wykonywania zdjęć aparatem.

**Poza zakresem prototypu:** generowanie i wysyłka linków, sprawdzanie ich ważności, powrót do sprawy po zakończeniu sesji, przypomnienia, nagrywanie wideo, aplikacje natywne, wysyłka zdjęć, panel pracownika i ocena zdjęć przez AI.

### Obowiązkowy zakres MVP

MVP obejmuje ścieżkę klienta od otwarcia linku do zakończenia inspekcji po zapisaniu kompletu ośmiu zdjęć. Serwer przechowuje zdjęcia, akceptację regulaminu oraz stan inspekcji przypisany do sprawy.

| Obszar | Wymaganie MVP |
|---|---|
| Zapis zdjęć | Po wybraniu „Zatwierdź zdjęcie” aplikacja zapisuje zdjęcie na serwerze dla danej sprawy i rodzaju ujęcia. Licznik uwzględnia ujęcie po potwierdzeniu zapisu przez serwer. |
| Wznowienie | Ponowne otwarcie tego samego ważnego linku przywraca zapisaną akceptację regulaminu, postęp i zatwierdzone zdjęcia. Klient trafia do pierwszego brakującego ujęcia lub do podsumowania, jeśli zapisano komplet. |
| Poprawa zdjęcia | Po potwierdzeniu zapisu nowe zdjęcie zastępuje poprzednie dla tego samego ujęcia. Jeśli zapis się nie powiedzie, dotychczasowe zdjęcie pozostaje w komplecie. |
| Zakończenie | Klient wybiera „Zakończ” po zapisaniu wszystkich ośmiu ujęć. Serwer oznacza inspekcję jako zakończoną. Ponowne otwarcie ważnego linku do zakończonej sprawy pokazuje potwierdzenie bez możliwości edycji. |

**Poza zakresem MVP** pozostają automatyczne generowanie i wysyłka linków, przypomnienia, panel pracownika i ocena zdjęć przez AI. Do testów MVP wystarczą wcześniej przygotowane sprawy z indywidualnymi linkami.

## 4. Ekrany prototypu w kolejności głównej ścieżki

Główna ścieżka: klient otwiera link do swojej sprawy, akceptuje przykładowy regulamin, dodaje i zatwierdza osiem zdjęć, sprawdza komplet i kończy demonstrację.

1. **Ekran powitalny**: Klient widzi dane swojego pojazdu, datę zlecenia, termin i listę ujęć jakie będzie musiał wykonać. Zapoznaje się z regulaminem i zaznacza akceptację, aby odblokować „Rozpocznij zdjęcia”.
2. **Dobry kadr. Krok po kroku.** Klient widzi instrukcję, przykład kadrowania i postęp. Wybiera „Wykonaj zdjęcie”. Sprawdza podgląd, w razie potrzeby wybiera „Powtórz”, a potem „Zatwierdź zdjęcie”.
3. **Osiem zdjęć. Komplet.** Klient przegląda osiem podpisanych miniatur. Może wrócić do wybranego ujęcia, a po sprawdzeniu zestawu wybiera „Zakończ”.
4. **Dziękujemy za wykonanie zdjęć.** Klient widzi dane pojazdu, liczbę zdjęć i informację, że zakończył oględziny.

## 5. Historie użytkownika i kryteria odbioru prototypu

### US1 · Otwarcie sprawy i akceptacja regulaminu

Jako klient chcę otworzyć otrzymany link na telefonie i sprawdzić dane pojazdu oraz zasady oględzin, żeby zacząć od właściwej sprawy.

- **K1.** Link otwiera ekran przygotowania dla wskazanego pojazdu.

  **Sprawdzam:** otwieram link do sprawy w nowej karcie na telefonie. **Zaliczone, gdy** od razu widzę markę, model, numer rejestracyjny i termin z tej sprawy oraz przykładowy regulamin.

- **K2.** Wykonywanie zdjęć można rozpocząć po zaakceptowaniu regulaminu.

  **Sprawdzam:** sprawdzam przycisk „Rozpocznij zdjęcia” przed zaznaczeniem pola, po zaznaczeniu i po odznaczeniu. **Zaliczone, gdy** przycisk jest aktywny wyłącznie przy zaznaczonym polu, a jego dotknięcie otwiera ujęcie „Przód pojazdu”.

### US2 · Wykonanie i zatwierdzenie ośmiu ujęć

Jako klient chcę widzieć instrukcję i podgląd każdego zdjęcia, żeby samodzielnie przygotować komplet do oględzin.

- **K1.** Każdy krok pokazuje nazwę ujęcia, instrukcję i przykład kadrowania.

  **Sprawdzam:** przechodzę wszystkie kroki. **Zaliczone, gdy** dla każdego widzę te trzy elementy, a ujęcia następują w kolejności: przód, tył, lewy bok, prawy bok, licznik, VIN, pierwsza strona dowodu rejestracyjnego, druga strona dowodu rejestracyjnego.

- **K2.** Zdjęcie wykonane telefonem pojawia się w podglądzie i można je wymienić przed zatwierdzeniem.

  **Sprawdzam:** dotykam „Wykonaj zdjęcie”, robię zdjęcie, wybieram „Powtórz” i najpierw anuluję wybór, a potem dodaję inne zdjęcie. **Zaliczone, gdy** po anulowaniu nadal widzę poprzednie zdjęcie, a po ponownej próbie podgląd pokazuje nowe.

- **K3.** Licznik uwzględnia wyłącznie zatwierdzone ujęcia, a podsumowanie otwiera się po zebraniu całego kompletu.

  **Sprawdzam:** przy stanie 7/8 dodaję ósme zdjęcie i zatwierdzam je po obejrzeniu podglądu. **Zaliczone, gdy** przed zatwierdzeniem widzę 7/8 i pozostaję na ekranie ujęcia, a po zatwierdzeniu widzę podsumowanie 8/8.

### US3 · Sprawdzenie kompletu i zakończenie demonstracji

Jako klient chcę sprawdzić i poprawić zdjęcia przed zakończeniem, żeby mieć komplet przypisany do właściwego pojazdu.

- **K1.** Podsumowanie pokazuje dane pojazdu i osiem podpisanych miniatur. Klient może poprawić pojedyncze ujęcie.

  **Sprawdzam:** wybieram miniaturę „Licznik”, dodaję inne zdjęcie i je zatwierdzam. **Zaliczone, gdy** wracam do podsumowania tego samego pojazdu, zmieniła się tylko miniatura licznika, a licznik nadal pokazuje 8/8.

- **K2.** „Zakończ” kończy demonstrację i wyświetla potwierdzenie.

  **Sprawdzam:** wybieram „Zakończ” przy otwartym panelu sieciowym przeglądarki. **Zaliczone, gdy** potwierdzenie wskazuje właściwy pojazd, osiem zdjęć i informację o symulacji, a panel sieciowy nie pokazuje żądania przesyłającego zdjęcia.

**Odbiór całej ścieżki.** Klient otwiera link na telefonie i wykonuje osiem ujęć bez podpowiedzi testera. Test jest zaliczony, gdy klient dochodzi do potwierdzenia, a tester uznaje wszystkie osiem zdjęć za zgodne z instrukcjami. Na każdym telefonie z uzgodnionej listy tester sprawdza też, czy zdjęcie wykonane aparatem otwiera się w podglądzie (US2, K2).

## 6. Kryteria odbioru MVP

### US4 · Zapisuję zdjęcia w trakcie inspekcji

- Po zatwierdzeniu ujęcia zapisuję je na serwerze. Po ponownym otwarciu sprawy zdjęcie jest dostępne przy właściwym ujęciu i wlicza się do postępu.
- Przerywam połączenie podczas zapisu. Jeśli zdjęcie nie zostało zapisane, aplikacja pokazuje błąd i pozwala ponowić zapis. Ponowienie po utracie odpowiedzi serwera nie tworzy dodatkowego ujęcia ani nie zwiększa licznika drugi raz.
- Próbuję zastąpić zapisane zdjęcie i zapis się nie udaje. Po ponownym otwarciu sprawy nadal widzę dotychczasowe zdjęcie. Po udanej podmianie zmienia się wyłącznie zdjęcie przypisane do tego ujęcia.

### US5 · Wracam do rozpoczętej inspekcji

- Akceptuję regulamin, zatwierdzam trzy zdjęcia i zamykam przeglądarkę. Otwieram ten sam ważny link w nowej sesji. Widzę postęp 3/8, przechodzę do czwartego ujęcia i mogę podejrzeć zapisane zdjęcia bez ponownej akceptacji regulaminu.
- Zamykam przeglądarkę po zapisaniu ośmiu zdjęć, zanim wybiorę „Zakończ”. Po otwarciu linku wracam do podsumowania 8/8 i mogę zakończyć inspekcję.
- Otwieram link po upływie pięciu dni od zlecenia. Widzę komunikat o wygaśnięciu. Serwer blokuje odczyt zdjęć i dalszą edycję również wtedy, gdy ekran inspekcji był już otwarty.

### US6 · Kończę inspekcję

- Przycisk „Zakończ” jest dostępny po zapisaniu ośmiu wymaganych ujęć. Potwierdzenie pojawia się po zapisaniu przez serwer stanu zakończenia. Gdy zapis się nie powiedzie, mogę ponowić zakończenie.
- Po zakończeniu otwieram ten sam ważny link. Widzę potwierdzenie dla tego samego pojazdu. Serwer odrzuca dalsze próby zmiany zdjęć.

## 7. Kierunek budowy

- **Stan prototypu** — zdjęcia i postęp pozostają w pamięci bieżącej karty. Zakończenie demonstracji pokazuje potwierdzenie. Odświeżenie lub zamknięcie karty kończy sesję bez zachowania postępu.
- **Płatne API z własnym kluczem** — nie.
- **Kierunek** — front dla klienta będzie częścią większej platformy do zarządzania oględzinami online. Platfroma będzie generować linki oraz udostępniać front dla pracowników, który będą zapoznawać się z wybraną częścią przesłanych wyników. Ponadto platforma będzie automatycznie (z wykorzystaniem AI) analizować przesłane zdjęcia.
- **Stan MVP** — serwer przechowuje zdjęcia i stan sprawy niezależnie od sesji przeglądarki. Zdjęcie widoczne tylko w podglądzie przed zatwierdzeniem jest robocze i po zamknięciu sesji klient wykonuje je ponownie.
- **Dostęp w MVP** — indywidualny link daje dostęp do jednej sprawy bez logowania i kodu SMS. Serwer sprawdza ważność linku przy odczycie danych i zdjęć oraz przy każdej próbie zapisu.

## 8. Wygląd

**Źródło wyglądu** — [DESIGN.md](DESIGN.md). [Prototyp](index.html) korzysta z oprawy Fotoinspekcji, w tym z fioletowej kolorystyki, panelu postępu i wzorów kadrów.
