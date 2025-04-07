# Dokument wymagań produktu (PRD) - AI Fiszki

## 1. Przegląd produktu

Aplikacja "AI Fiszki" to narzędzie webowe, które usprawnia proces tworzenia fiszek edukacyjnych. Wykorzystuje ona sztuczną inteligencję do generowania propozycji fiszek na podstawie wprowadzonego tekstu oraz umożliwia ich recenzję i modyfikację. Dodatkowo, aplikacja wspiera ręczne tworzenie fiszek, a także ich edycję, usuwanie oraz integrację z biblioteką open-source do powtórek, co optymalizuje proces nauki poprzez metodę spaced repetition.

## 2. Problem użytkownika

Użytkownicy często rezygnują z ręcznego tworzenia fiszek, ponieważ proces ten jest czasochłonny i wymaga dużego nakładu pracy. Początkujący użytkownicy mają również trudności z optymalnym podziałem informacji między "przód" a "tył" fiszki, co skutkuje mniej efektywną nauką. Rozwiązaniem jest automatyzacja generowania fiszek przy użyciu AI, która przyspiesza proces tworzenia, oraz zapewnienie intuicyjnego interfejsu do recenzji i ręcznej edycji fiszek.

## 3. Wymagania funkcjonalne

1. Generowanie fiszek przez AI:
   - Użytkownik wprowadza tekst (kopiuj-wklej), na podstawie którego AI generuje propozycje fiszek.
   - Wygenerowane fiszki są prezentowane do recenzji, gdzie użytkownik może je zatwierdzić, edytować lub odrzucić.

2. Ręczne tworzenie fiszek:
   - Formularz umożliwiający wpisanie treści "przód" (maks. 200 znaków) oraz "tył" (maks. 500 znaków).
   - Walidacja pól z wyraźnymi komunikatami przy przekraczaniu limitów znaków.
   - Ręczne tworzenie fiszek i wyświetlanie w ramach widoku listy "Moje fiszki"

3. Zarządzanie fiszkami:
   - Przeglądanie, edycja i usuwanie fiszek zapisanych w systemie.
   - Sortowanie i filtrowanie fiszek według daty utworzenia oraz statusu (zatwierdzone, edytowane, odrzucone).

4. System kont użytkowników:
   - Rejestracja i logowanie, umożliwiające bezpieczny dostęp do aplikacji i przechowywanie fiszek.
   - Przechowywanie minimalnych danych, takich jak czas generowania fiszki i identyfikator twórcy.
   - Fiszki są przypisane do indywidualnych kont użytkowników i dostępne wyłącznie dla ich właściciela. Użytkownicy nie mają możliwości przeglądania ani edytowania fiszek innych użytkowników.

5. Integracja z algorytmem powtórek:
   - Po zatwierdzeniu fiszki, integracja z wybraną open-source'ową biblioteką do powtórek, wspierającą metodę spaced repetition.

6. Statystyki generowania fiszek:
   - System zbiera dane dotyczące generowania fiszek przez AI.
   - Wyświetla procent fiszek wygenerowanych przez AI, które zostały zaakceptowane przez użytkowników, umożliwiając monitorowanie efektywności procesu generowania.

## 4. Granice produktu

- Nie obejmuje implementacji zaawansowanego algorytmu powtórek (np. SuperMemo, Anki).
- Brak wsparcia dla importu fiszek z wielu formatów (PDF, DOCX, itp.).
- Nie przewiduje funkcji współdzielenia zestawów fiszek między użytkownikami.
- Brak integracji z innymi platformami edukacyjnymi.
- MVP jest realizowane wyłącznie jako aplikacja webowa; aplikacje mobilne nie są obecnie planowane.
- Nie wdraża się rozszerzonych mechanizmów zabezpieczeń (np. potwierdzenie e-mail, 2FA) ani zaawansowanego monitorowania integracji z usługą AI.

## 5. Historyjki użytkowników

US-001
Tytuł: Rejestracja i logowanie
Opis: Jako potencjalny użytkownik chcę utworzyć konto oraz zalogować się do systemu, aby mieć dostęp do swoich fiszek i korzystać z pełnych funkcji aplikacji.
Kryteria akceptacji:
- Użytkownik może zarejestrować konto poprzez podanie podstawowych danych (np. e-mail, hasło).
- System umożliwia logowanie oraz autoryzowany dostęp do funkcji aplikacji.

US-002
Tytuł: Generowanie fiszek przez AI
Opis: Jako użytkownik chcę wprowadzić tekst, by AI wygenerowało propozycje fiszek, co pozwoli mi szybciej tworzyć materiały do nauki.
Kryteria akceptacji:
- Po wprowadzeniu tekstu (od 1000 do 10000 znaków), system komunikuje się z API modelu LLM i wyświetla listę wygenerowanych propozycji fiszek do akceptacji przez uytkownika.
- Każda fiszka zawiera dwa pola: "przód" (do 200 znaków) oraz "tył" (do 500 znaków).
- Propozycje są wyświetlane w interfejsie recenzji.

US-003
Tytuł: Recenzja fiszek generowanych przez AI
Opis: Jako użytkownik chcę móc przeglądać propozycje fiszek generowanych przez AI, aby móc je zatwierdzić, edytować lub odrzucić.
Kryteria akceptacji:
- System umożliwia wyświetlenie listy wygenerowanych fiszek.
- Użytkownik ma możliwość zatwierdzenia, edycji lub odrzucenia każdej fiszki.
- Proces recenzji odbywa się w czasie rzeczywistym; odrzucenie wszystkich propozycji kończy proces generacji bez opcji ponownej generacji.
- Zatwierdzone fiszki są zapisywane w bazie danych i dostępne w sekcji "Moje fiszki"

US-004
Tytuł: Ręczne tworzenie fiszek
Opis: Jako użytkownik chcę tworzyć fiszki ręcznie, aby móc wprowadzać spersonalizowane treści, gdy propozycje AI nie spełniają moich oczekiwań.
Kryteria akceptacji:
- Formularz umożliwia wpisanie treści "przód" (maks. 200 znaków) oraz "tył" (maks. 500 znaków).
- Walidacja pól zapobiega przekroczeniu dozwolonych limitów znaków.
- Ręcznie utworzone fiszki są zapisywane i zarządzane analogicznie do fiszek generowanych przez AI.

US-005
Tytuł: Zarządzanie fiszkami
Opis: Jako użytkownik chcę przeglądać, edytować i usuwać zapisane fiszki, aby skutecznie nimi zarządzać.
Kryteria akceptacji:
- Użytkownik widzi listę wszystkich swoich fiszek.
- Fiszki można edytować lub usuwać, a zmiany są zapisywane w czasie rzeczywistym.

US-006
Tytuł: Sortowanie i filtrowanie fiszek
Opis: Jako użytkownik chcę sortować i filtrować zapisane fiszki, aby szybko odnaleźć te, które są mi potrzebne.
Kryteria akceptacji:
- System umożliwia sortowanie fiszek według daty utworzenia oraz innych kryteriów.
- System pozwala na filtrowanie fiszek według statusu (zatwierdzone, edytowane, odrzucone).

US-007
Tytuł: Sesja nauki fiszek
Opis: Jako użytkownik chcę przeprowadzić sesję nauki, w której zewnętrzny algorytm przygotuje sesję nauki fiszek. Na start wyświetlany jest przód fiszki, a poprzez interakcję użytkownik wyświetla jej tył. Następnie użytkownik ocenia, na ile przyswoił fiszkę, po czym algorytm prezentuje kolejną fiszkę.
Kryteria akceptacji:
- Algorytm przygotowuje sesję nauki na podstawie dostępnych fiszek.
- Na początku prezentowany jest jedynie przód fiszki.
- Użytkownik ma możliwość interaktywnego wyświetlenia tyłu fiszki.
- Użytkownik może ocenić, w jakim stopniu przyswoił dane informacje (np. poprzez wybór poziomu trudności lub procentową ocenę).
- Po ocenie, system prezentuje kolejną fiszkę.

## 6. Metryki sukcesu

- Co najmniej 75% fiszek wygenerowanych przez AI musi być zaakceptowanych przez użytkownika.
- Użytkownicy korzystają z funkcji AI przy tworzeniu przynajmniej 75% wszystkich fiszek.
- System charakteryzuje się szybkim czasem generowania i recenzji fiszek.
- Interfejs użytkownika jest responsywny oraz kompatybilny z popularnymi przeglądarkami (Chrome, Safari) i urządzeniami mobilnymi. 