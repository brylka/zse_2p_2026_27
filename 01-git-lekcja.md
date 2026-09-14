# Git – pierwsze kroki

**Pracownia projektowania oprogramowania | Technik programista | Klasa II**
Dział I: Warsztat projektanta – narzędzia pracy
Efekt kształcenia: **INF.04.3.5** – *korzysta z systemu kontroli wersji, np. Git*
Opracował: **Bartosz Bryniarski**

---

## Cele lekcji

Po tej lekcji potrafisz:

- wyjaśnić, czym jest system kontroli wersji i po co się go używa,
- skonfigurować Gita na swoim stanowisku (`git config`),
- utworzyć repozytorium w katalogu projektu (`git init`),
- sprawdzić stan plików (`git status`),
- zapisać zmiany w historii projektu (`git add`, `git commit`),
- przejrzeć historię zmian (`git log`),
- wykluczyć pliki z repozytorium przy pomocy `.gitignore`.

---

## 1. Po co komu kontrola wersji?

Każdy programista zna ten katalog:

```
projekt/
├── index.html
├── index_stary.html
├── index_KOPIA.html
├── index_final.html
├── index_final_POPRAWIONY.html
└── index_final_POPRAWIONY_v2_TEN_DZIAŁA.html
```

Problemy takiego „systemu":

| Problem | Skutek |
|---|---|
| Nie wiadomo, który plik jest aktualny | Tracisz czas, nadpisujesz dobrą wersję |
| Nie wiadomo, **co** się zmieniło między wersjami | Nie da się znaleźć momentu, w którym pojawił się błąd |
| Nie wiadomo, **kto** i **kiedy** zmienił | W pracy zespołowej – chaos |
| Kopie zajmują miejsce i mnożą się | Katalog nie do ogarnięcia po miesiącu |

**System kontroli wersji (VCS – *Version Control System*)** rozwiązuje to za Ciebie: przechowuje jeden zestaw plików + całą historię ich zmian.

> **Definicja.** System kontroli wersji to narzędzie rejestrujące zmiany w plikach w czasie, tak aby można było wrócić do dowolnej wcześniejszej wersji, porównać wersje i pracować równolegle w zespole.

### Git – kilka faktów

- Powstał w **2005 r.**, autor: **Linus Torvalds** (twórca Linuksa), na potrzeby rozwoju jądra Linuksa.
- Jest **rozproszony** (*distributed*) – każdy programista ma u siebie pełną kopię historii projektu. Można pracować bez internetu.
- Jest darmowy i otwartoźródłowy.
- To **standard branżowy** – praktycznie każda firma programistyczna go używa.

### Git ≠ GitHub

To bardzo częsta pomyłka:

| **Git** | **GitHub** |
|---|---|
| Program na Twoim komputerze | Serwis internetowy (strona WWW) |
| Zarządza historią lokalnie | Przechowuje repozytoria zdalnie |
| Działa bez internetu | Wymaga połączenia |
| Alternatywy: brak realnej | Alternatywy: GitLab, Bitbucket |

Na dzisiejszej lekcji pracujemy **wyłącznie lokalnie** – GitHub będzie na kolejnych zajęciach.

---

## 2. Podstawowe pojęcia

| Pojęcie | Znaczenie |
|---|---|
| **repozytorium** (*repository, repo*) | Katalog projektu wraz z ukrytym folderem `.git`, w którym Git trzyma całą historię |
| **commit** | Zapisany „punkt kontrolny" – migawka projektu w danym momencie, z opisem i autorem |
| **working directory** | Katalog roboczy – pliki, które właśnie edytujesz |
| **staging area** (*poczekalnia*, indeks) | Miejsce, gdzie zbierasz zmiany przeznaczone do najbliższego commita |
| **hash** | Unikalny identyfikator commita, np. `a3f5c91` (skrót z 40-znakowego SHA-1) |
| **HEAD** | Wskaźnik na commit, na którym aktualnie się znajdujesz |

### Trzy stany pliku

Zapamiętaj tę drogę – to serce Gita:

```
  KATALOG ROBOCZY         POCZEKALNIA            REPOZYTORIUM
  (working directory)     (staging area)         (.git)

   edytujesz plik   →   git add   →   git commit   →   zapisane
                                                        w historii
```

Analogia: **paczka kurierska**

1. *Katalog roboczy* – rzeczy leżą po całym pokoju.
2. `git add` – wkładasz wybrane rzeczy do pudełka.
3. `git commit` – zaklejasz pudełko, przyklejasz karteczkę z opisem i odkładasz na półkę. Od tej chwili zawartość jest zachowana na zawsze.

---

## 3. Konfiguracja – robisz to raz

Git podpisuje każdy commit imieniem i adresem e-mail autora. Zanim zrobisz pierwszy commit, musisz mu je podać.

```bash
git config --global user.name "Jan Kowalski"
git config --global user.email "jan.kowalski@example.com"
```

Sprawdzenie ustawień:

```bash
git config --list
git --version
```

**`--global`** = ustawienie dla wszystkich Twoich projektów na tym koncie. Bez tego przełącznika ustawienie dotyczy tylko bieżącego repozytorium.

> **Uwaga w pracowni:** jeśli pracujesz na koncie współdzielonym, ustaw dane **bez** `--global`, już wewnątrz swojego repozytorium – inaczej nadpiszesz konfigurację koledze.

---

## 4. Zestaw poleceń na dziś

### `git init` – tworzy repozytorium

```bash
mkdir moj-projekt
cd moj-projekt
git init
```

Powstaje ukryty katalog `.git` – to w nim siedzi cała historia. **Nigdy go nie usuwaj ani nie edytuj ręcznie.**

Podejrzenie ukrytych plików: `ls -a` (Linux/macOS) lub `dir /a` (Windows).

### `git status` – co się dzieje w repozytorium

```bash
git status
```

Najważniejsze polecenie na początku nauki. Mówi Ci:

- które pliki są nowe i nieśledzone (*untracked*),
- które zmodyfikowane (*modified*),
- które czekają w poczekalni (*staged*).

Uruchamiaj je **po każdej operacji**, dopóki nie nabierzesz wprawy.

### `git add` – dodaje zmiany do poczekalni

```bash
git add index.html        # konkretny plik
git add style.css app.js  # kilka plików
git add .                 # wszystkie zmiany w bieżącym katalogu i podkatalogach
```

### `git commit` – zapisuje punkt kontrolny

```bash
git commit -m "Dodanie strony głównej"
```

Przełącznik `-m` podaje opis (*commit message*). Bez niego Git otworzy edytor tekstu.

**Dobre opisy commitów:**

| ✅ Dobrze | ❌ Źle |
|---|---|
| `Dodanie formularza kontaktowego` | `zmiany` |
| `Poprawa walidacji adresu e-mail` | `poprawki` |
| `Usunięcie nieużywanych stylów CSS` | `asdfgh` |
| `Zmiana koloru nagłówka na granatowy` | `.` |

Zasada: opis ma odpowiadać na pytanie **„co robi ten commit?"**. Tryb rzeczownikowy lub rozkazujący, do ok. 50 znaków.

### `git log` – historia zmian

```bash
git log                    # pełna historia
git log --oneline          # jedna linia na commit – najczęściej używane
git log --oneline --graph  # z graficzną strukturą
git log -3                 # ostatnie 3 commity
```

Przykładowy wynik `git log --oneline`:

```
c4e1a09 Dodanie stopki z danymi kontaktowymi
9b2f7d3 Poprawa literówki w nagłówku
a3f5c91 Pierwszy commit - szkielet strony
```

Jeśli historia nie mieści się na ekranie, Git otwiera przeglądarkę tekstu – **wyjście klawiszem `q`**.

### `git show` – szczegóły jednego commita

```bash
git show a3f5c91
```

---

## 5. Plik `.gitignore`

Nie wszystko powinno trafiać do repozytorium: pliki tymczasowe, katalogi środowiska, hasła, pliki konfiguracyjne edytora.

Utwórz w katalogu głównym projektu plik o nazwie `.gitignore`:

```gitignore
# Środowisko Pythona
venv/
__pycache__/
*.pyc

# Ustawienia edytorów i IDE
.vscode/
.idea/

# Systemowe
Thumbs.db
.DS_Store

# Dane wrażliwe
haslo.txt
.env
```

Zasady:

- jedna reguła na linię,
- `#` rozpoczyna komentarz,
- `*` zastępuje dowolny ciąg znaków (`*.log` = wszystkie pliki `.log`),
- `/` na końcu oznacza katalog.

**Ważne:** `.gitignore` działa tylko na pliki **jeszcze nieśledzone**. Jeśli plik został już zacommitowany, dopisanie go do `.gitignore` nic nie da.

Sam plik `.gitignore` **dodajemy** do repozytorium – ma obowiązywać cały zespół.

---

## 6. Koniec zajęć: usuń swoje dane z komputera

Komputery w pracowni są **wspólne**. Wszystko, co ustawiłeś poleceniem `git config --global`, zostaje na tym stanowisku i dotyczy **następnej osoby**, która przy nim usiądzie.

Co się stanie, jeśli tego nie posprzątasz:

- kolejny uczeń zrobi commity **podpisane Twoim imieniem i adresem e-mail**,
- od momentu, gdy dojdzie GitHub (kolejne lekcje), ktoś może **wypchnąć cudze pliki na Twoje konto**.

Dlatego na koniec każdych zajęć wykonaj poniższe kroki.

### Krok 1. Usuń swoje dane z konfiguracji Gita

```bash
git config --global --unset user.name
git config --global --unset user.email
```

Sprawdzenie – lista powinna być pusta lub bez Twoich danych:

```bash
git config --global --list
```

### Krok 2. Usuń zapamiętane logowanie do GitHuba (Windows)

Dotyczy kolejnych lekcji, gdy zaczniemy wysyłać kod na GitHuba. Windows po pierwszym `push` zapamiętuje poświadczenia.

`Win + R`, a następnie:

```
control /name Microsoft.CredentialManager
```

→ **Poświadczenia systemu Windows** → wpis `git:https://github.com` → **Usuń**.

To samo z poziomu PowerShella:

```powershell
cmdkey /delete:git:https://github.com
```

Kontrola – pusta odpowiedź oznacza, że nic nie zostało:

```powershell
cmdkey /list | findstr github
```

### Krok 3. Wyloguj się z GitHuba w przeglądarce

Zamknięcie karty **nie wystarczy**. Menu profilu → *Sign out*. Jeśli korzystałeś z okna prywatnego, wystarczy je zamknąć.

### Krok 4. Usuń pliki projektu ze stanowiska

Skopiuj katalog projektu na pendrive lub swój dysk w chmurze, a potem usuń go z dysku lokalnego – razem z ukrytym katalogiem `.git`. Pamiętaj też o opróżnieniu Kosza.

---

> **Na początku każdych zajęć** ustawiasz `user.name` i `user.email` od nowa. To 30 sekund – a chroni Twoje konto i Twoje nazwisko.

**Zasada działa w obie strony:** jeśli zastaniesz stanowisko z cudzym loginem albo cudzą konfiguracją Gita – nie korzystaj z tego, tylko wyloguj poprzednią osobę.

---

## 7. Ściąga

| Polecenie | Działanie |
|---|---|
| `git --version` | Sprawdza wersję Gita |
| `git config --global user.name "..."` | Ustawia imię i nazwisko autora |
| `git config --global user.email "..."` | Ustawia e-mail autora |
| `git init` | Tworzy nowe repozytorium |
| `git status` | Pokazuje stan plików |
| `git add <plik>` | Dodaje plik do poczekalni |
| `git add .` | Dodaje wszystkie zmiany |
| `git commit -m "opis"` | Zapisuje commit z opisem |
| `git log` | Wyświetla historię |
| `git log --oneline` | Historia skrócona |
| `git show <hash>` | Szczegóły commita |
| `git config --global --unset user.name` | Usuwa dane autora ze stanowiska (po zajęciach) |
| `git config --global --unset user.email` | Usuwa e-mail autora ze stanowiska (po zajęciach) |

---

# ĆWICZENIA

Wszystkie ćwiczenia wykonujesz w terminalu (Git Bash / PowerShell / terminal Linuksa).

---

## Ćwiczenie 1 – Sprawdzenie i konfiguracja (5 min)

1. Sprawdź, czy Git jest zainstalowany:
   ```bash
   git --version
   ```
   Zapisz wynik: ................................................

2. Ustaw swoje dane (użyj prawdziwego imienia i nazwiska – tak podpiszesz swoje commity):
   ```bash
   git config --global user.name "Twoje Imię Nazwisko"
   git config --global user.email "twoj@email.pl"
   ```

3. Sprawdź, czy dane się zapisały:
   ```bash
   git config user.name
   git config user.email
   ```

---

## Ćwiczenie 2 – Pierwsze repozytorium (10 min)

1. Utwórz katalog `wizytowka` i wejdź do niego:
   ```bash
   mkdir wizytowka
   cd wizytowka
   ```

2. Zainicjuj repozytorium:
   ```bash
   git init
   ```

3. Sprawdź, czy powstał katalog `.git`:
   ```bash
   ls -a
   ```

4. Uruchom `git status`. **Co Git wypisuje o commitach?**

   .....................................................................

5. Utwórz plik `index.html` o treści:
   ```html
   <!DOCTYPE html>
   <html lang="pl">
   <head>
     <meta charset="UTF-8">
     <title>Moja wizytówka</title>
   </head>
   <body>
     <h1>Jan Kowalski</h1>
   </body>
   </html>
   ```

6. Ponownie uruchom `git status`. **W jakiej sekcji pojawił się `index.html`?**

   .....................................................................

7. Dodaj plik do poczekalni i sprawdź status **jeszcze raz**:
   ```bash
   git add index.html
   git status
   ```
   **Co się zmieniło w komunikacie? Jakim kolorem wyświetla się teraz nazwa pliku?**

   .....................................................................

8. Zrób pierwszy commit:
   ```bash
   git commit -m "Pierwszy commit - szkielet wizytówki"
   ```

9. Uruchom `git status`. **Jaki komunikat oznacza, że wszystko jest zapisane?**

   .....................................................................

---

## Ćwiczenie 3 – Budowanie historii (10 min)

Wykonaj poniższe kroki. **Po każdej zmianie rób osobny commit z sensownym opisem.**

1. Dodaj do `<body>` akapit z zawodem, np. `<p>Uczeń technikum programistycznego</p>`
   → commit
2. Utwórz plik `style.css` z regułą zmieniającą kolor tła strony, podepnij go w `<head>`
   → commit
3. Dodaj listę `<ul>` z trzema swoimi zainteresowaniami
   → commit

Następnie:

4. Wyświetl historię:
   ```bash
   git log --oneline
   ```
   **Ile commitów widzisz?** ...........

5. Przepisz ich skróty (hashe) i opisy:

   | Hash | Opis commita |
   |---|---|
   | | |
   | | |
   | | |
   | | |

6. Sprawdź szczegóły **pierwszego** (najstarszego) commita:
   ```bash
   git show <hash>
   ```
   **Kto jest autorem? Jaka jest data?**

   .....................................................................

---

## Ćwiczenie 4 – `.gitignore` (7 min)

1. W katalogu `wizytowka` utwórz plik `notatki.txt` z dowolną treścią oraz katalog `tymczasowe` z jednym plikiem w środku.

2. Uruchom `git status` – oba powinny być widoczne jako nieśledzone.

3. Utwórz plik `.gitignore` o treści:
   ```gitignore
   notatki.txt
   tymczasowe/
   ```

4. Uruchom `git status` ponownie.
   **Które pliki zniknęły z listy? Który nowy plik się pojawił?**

   .....................................................................

5. Zacommituj plik `.gitignore`:
   ```bash
   git add .gitignore
   git commit -m "Dodanie pliku .gitignore"
   ```

---

## Ćwiczenie 5 – Zadanie problemowe (8 min)

Kolega z klasy pokazuje Ci swój terminal:

```
$ git status
On branch main
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   app.py

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
        modified:   index.html

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        haslo.txt
```

Odpowiedz:

**a)** Który plik trafi do repozytorium, jeśli kolega wykona teraz `git commit -m "zmiany"`?

.....................................................................

**b)** Co musi zrobić, żeby do tego samego commita trafiły zmiany w `index.html`?

.....................................................................

**c)** Co poradzisz mu w sprawie pliku `haslo.txt`? Podaj konkretne polecenie lub czynność.

.....................................................................

**d)** Zaproponuj lepszy opis commita niż `"zmiany"`.

.....................................................................

---

## Zadanie domowe (nieobowiązkowe)

Załóż repozytorium dla dowolnego swojego wcześniejszego projektu (z programowania, stron WWW, baz danych). Dodaj sensowny `.gitignore` i podziel istniejący kod na **co najmniej 3 commity** o logicznych opisach. Na kolejnych zajęciach wypchniemy takie repozytorium na GitHuba.

---

## Kryteria oceny ćwiczeń

| Kryterium | Punkty |
|---|---|
| Poprawna konfiguracja `user.name` i `user.email` | 1 |
| Utworzone repozytorium z plikiem `index.html` i pierwszym commitem | 2 |
| Minimum 4 commity o czytelnych, opisowych komunikatach | 3 |
| Poprawnie działający `.gitignore` (zacommitowany) | 2 |
| Odpowiedzi na pytania z ćwiczenia 5 | 2 |
| **Razem** | **10** |

---

## Najczęstsze błędy początkujących

1. **`git init` w złym katalogu** (np. w `Dokumenty` albo na pulpicie) – Git zaczyna śledzić wszystko. Zawsze sprawdź `pwd` przed `git init`.
2. **Commit bez `git add`** – Git zapisuje tylko to, co jest w poczekalni.
3. **Opisy typu „zmiany", „poprawki"** – za pół roku nikt (łącznie z Tobą) nie będzie wiedział, o co chodziło.
4. **Jeden ogromny commit na koniec dnia** – commituj małe, logicznie zamknięte porcje pracy.
5. **Wrzucanie haseł i kluczy API do repozytorium** – po commicie zostają w historii na zawsze.
6. **Usunięcie katalogu `.git`** – kasuje całą historię projektu bezpowrotnie.
