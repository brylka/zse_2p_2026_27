# Struktury danych – ćwiczenia

**Projektowanie oprogramowania | Technik programista | Klasa II**
Dział II: Projektowanie struktur danych
Efekty kształcenia: **INF.04.3.2**, **INF.04.3.1**
Opracował: **Bartosz Bryniarski**

---

## Jak korzystać z tego materiału

Ćwiczenia przypisane są do sześciu lekcji działu. Zadania oznaczone **[K]** wykonuje się na komputerze (konsola Pythona lub dowolne IDE), pozostałe rozwiązuje się na kartce.

Klucz odpowiedzi znajduje się na końcu pliku.

| Lekcja | Temat | Ćwiczenia |
|---|---|---|
| 1 | Tablice jednowymiarowe i dwuwymiarowe | 1.1 – 1.7 |
| 2 | Tablice dynamiczne i asocjacyjne | 2.1 – 2.6 |
| 3 | Typ rekordowy: struktura i unia | 3.1 – 3.6 |
| 4 | Typ plikowy i typ wskaźnikowy | 4.1 – 4.7 |
| 5 | Kolekcje: listy, kolejki, stosy, wektory | 5.1 – 5.7 |
| 6 | Projektowanie zestawu danych | 6.1 – 6.5 |

---

# Lekcja 1. Tablice jednowymiarowe i dwuwymiarowe

### Ćwiczenie 1.1 – Indeksy

Dla tablicy `int tab[8]` odpowiedz:

```
a)  indeks pierwszego elementu       = ______
b)  indeks ostatniego elementu       = ______
c)  liczba elementów                 = ______
d)  poprawny warunek pętli po całej tablicy:  for (i = 0; i ____ 8; i++)
e)  co się stanie przy odwołaniu tab[8] w Javie?  w C?
```

### Ćwiczenie 1.2 – Adresy w pamięci

Tablica `int tab[6]` zaczyna się pod adresem 2000, a typ `int` zajmuje 4 bajty.

| Element | Adres |
|---|---|
| `tab[0]` | 2000 |
| `tab[1]` | |
| `tab[3]` | |
| `tab[5]` | |

Zapisz wzór ogólny na adres elementu o indeksie `i`. Ile bajtów zajmuje cała tablica?

### Ćwiczenie 1.3 – Schematy przetwarzania

Napisz w pseudokodzie lub w Pythonie:

**a)** funkcję liczącą średnią arytmetyczną elementów tablicy,
**b)** funkcję zwracającą indeks wartości najmniejszej,
**c)** funkcję zliczającą, ile elementów jest większych od podanej wartości.

### Ćwiczenie 1.4 – Znajdź błąd

Każdy fragment zawiera jeden błąd. Wskaż go i popraw.

```c
a)  for (i = 1; i <= n; i++)  suma += tab[i];

b)  int maks = 0;
    for (i = 0; i < n; i++)  if (tab[i] > maks) maks = tab[i];

c)  for (i = 0; i < n; i++)  tab[i] = tab[i+1];   // przesunięcie w lewo
```

### Ćwiczenie 1.5 – Tablica dwuwymiarowa

Dana jest macierz `int m[3][4]` wypełniona kolejnymi liczbami od 1 do 12 (wierszami).

```
a)  m[0][0] = ______      c)  m[2][3] = ______
b)  m[1][2] = ______      d)  m[2][0] = ______
```

**e)** Napisz podwójną pętlę wypisującą sumę każdego wiersza osobno.
**f)** Napisz pętlę liczącą sumę elementów na przekątnej macierzy kwadratowej.

### Ćwiczenie 1.6 – Układ w pamięci

Macierz 2 × 3 zawiera wartości:

```
[7, 8, 9]
[1, 2, 3]
```

**a)** Zapisz kolejność bajtów przy układzie wierszami.
**b)** Zapisz kolejność przy układzie kolumnami.
**c)** Który układ stosuje język C, a który Fortran?

### Ćwiczenie 1.7 [K] – Szachownica

Napisz program wypisujący szachownicę 8 × 8 złożoną ze znaków `#` i `.`, używając tablicy dwuwymiarowej i warunku na sumie indeksów.

---

# Lekcja 2. Tablice dynamiczne i asocjacyjne

### Ćwiczenie 2.1 – Rozmiar a pojemność

Tablica dynamiczna startuje z pojemnością 2 i podwaja ją po zapełnieniu. Uzupełnij tabelę dla kolejnych dodawanych elementów:

| Po dodaniu elementu nr | Rozmiar | Pojemność | Czy nastąpiło przepisanie? |
|---|---|---|---|
| 1 | | | |
| 2 | | | |
| 3 | | | |
| 5 | | | |
| 9 | | | |

### Ćwiczenie 2.2 – Nazwy w językach

Uzupełnij tabelę.

| Język | Typ tablicy dynamicznej | Dodanie na koniec | Odczyt rozmiaru |
|---|---|---|---|
| Python | | | |
| Java | | | |
| C++ | | | |
| C# | | | |

### Ćwiczenie 2.3 – Tablica czy słownik

Dla każdego zastosowania wybierz strukturę i uzasadnij jednym zdaniem.

| Dane | Struktura | Uzasadnienie |
|---|---|---|
| Oceny ucznia w kolejności wystawiania | | |
| Liczba mieszkańców według nazwy miasta | | |
| Kolejka zgłoszeń do rozpatrzenia | | |
| Ustawienia programu (nazwa opcji i wartość) | | |
| Lista zakupów do odhaczania | | |
| Liczba wystąpień każdego słowa w tekście | | |

### Ćwiczenie 2.4 – Operacje na słowniku

Dany jest słownik:

```python
magazyn = {"srubki": 120, "nakretki": 80, "podkladki": 45}
```

Zapisz w Pythonie:

```
a)  dodanie pozycji "gwozdzie" z wartością 200
b)  zwiększenie liczby śrubek o 30
c)  sprawdzenie, czy w magazynie są wkręty
d)  usunięcie pozycji "podkladki"
e)  wypisanie wszystkich pozycji z wartością mniejszą niż 100
f)  policzenie łącznej liczby elementów w magazynie
```

### Ćwiczenie 2.5 – Klucz czy nie klucz

Rozstrzygnij, czy dana może być kluczem słownika. Odpowiedź uzasadnij.

```
a)  numer PESEL                          ___
b)  imię ucznia                          ___
c)  lista ocen                           ___
d)  adres e-mail                         ___
e)  data i godzina pomiaru               ___
f)  obiekt, którego pola zmieniają się w trakcie    ___
```

### Ćwiczenie 2.6 [K] – Licznik słów

Napisz program, który dla podanego zdania policzy, ile razy wystąpiło każde słowo, i wypisze wynik. Użyj słownika. Wyjaśnij, dlaczego lista byłaby tu gorszym wyborem.

---

# Lekcja 3. Typ rekordowy: struktura i unia

### Ćwiczenie 3.1 – Projekt rekordu

Zaprojektuj rekord opisujący **książkę w bibliotece**. Dla każdego pola podaj nazwę i typ prosty z działu I.

| Pole | Typ | Uzasadnienie |
|---|---|---|
| | | |
| | | |
| | | |
| | | |
| | | |

Minimum pięć pól. Uwzględnij co najmniej jedno pole logiczne.

### Ćwiczenie 3.2 – Tablice równoległe

Program przechowuje dane pracowników w trzech osobnych tablicach:

```c
char nazwiska[100][40];
int  wiek[100];
float pensja[100];
```

**a)** Wymień dwa problemy, jakie niesie takie rozwiązanie.
**b)** Przepisz to z użyciem struktury i tablicy rekordów.
**c)** Napisz pętlę wypisującą nazwiska osób zarabiających powyżej 5000.

### Ćwiczenie 3.3 – Rozmiar struktury

Oblicz rozmiar każdej struktury, zakładając: `char` 1 bajt, `int` 4 bajty, `double` 8 bajtów, wyrównanie do rozmiaru największego pola.

```c
a)  struct A { int x; int y; };                 = ______

b)  struct B { char c; int x; };                = ______

c)  struct C { char c; char d; int x; };        = ______

d)  union  D { int x; double y; char c[4]; };   = ______
```

Wyjaśnij, dlaczego wynik w podpunkcie `b` nie wynosi 5.

### Ćwiczenie 3.4 – Rekord zagnieżdżony

Zaprojektuj strukturę `Zamowienie`, która zawiera:

- numer zamówienia,
- dane klienta (nazwa, adres rozbity na ulicę, miasto i kod pocztowy),
- datę złożenia (dzień, miesiąc, rok),
- wartość zamówienia.

Zapisz definicję w dowolnej składni i pokaż, jak odwołać się do miasta klienta.

### Ćwiczenie 3.5 – Struktura a unia

Odpowiedz:

**a)** Czym różni się rozmiar struktury od rozmiaru unii o tych samych polach?
**b)** Ile pól unii ma sensowną wartość w danej chwili?
**c)** Po co stosuje się pole rozpoznawcze?
**d)** Podaj jedno praktyczne zastosowanie unii.

### Ćwiczenie 3.6 – Zaprojektuj unię z polem rozpoznawczym

Program przechowuje wynik pomiaru, który może być liczbą całkowitą, liczbą rzeczywistą albo komunikatem błędu. Zaprojektuj strukturę z unią i polem rozpoznawczym oraz napisz warunek wypisujący wartość we właściwy sposób.

---

# Lekcja 4. Typ plikowy i typ wskaźnikowy

### Ćwiczenie 4.1 – Tryby otwarcia

Dobierz tryb do zadania.

| Zadanie | Tryb |
|---|---|
| Wczytanie listy uczniów z pliku | |
| Zapis raportu od nowa, kasując poprzedni | |
| Dopisanie wpisu do dziennika zdarzeń | |
| Odczyt zdjęcia w formacie JPG | |

### Ćwiczenie 4.2 – Plik tekstowy czy binarny

Rozstrzygnij (T – tekstowy, B – binarny) i uzasadnij:

```
a)  eksport ocen do arkusza kalkulacyjnego     ___
b)  zapis stanu gry z pozycjami postaci        ___
c)  plik konfiguracyjny edytowany ręcznie      ___
d)  nagranie dźwiękowe                         ___
e)  wymiana danych z systemem innej firmy      ___
```

### Ćwiczenie 4.3 [K] – Praca z plikiem

Napisz program, który:
1. zapisze do pliku `oceny.txt` pięć ocen, każdą w osobnej linii,
2. wczyta plik i policzy średnią,
3. dopisze na końcu pliku linię z wyliczoną średnią.

Zwróć uwagę, żeby krok 3 nie skasował zawartości pliku.

### Ćwiczenie 4.4 – Dostęp swobodny

Plik zawiera rekordy o stałym rozmiarze 64 bajtów.

```
a)  pozycja rekordu nr 0    = ______
b)  pozycja rekordu nr 5    = ______
c)  wzór na pozycję rekordu nr i:  ______
d)  plik ma 20 480 bajtów - ile zawiera rekordów?  ______
```

**e)** Dlaczego ten sposób nie zadziała dla pliku tekstowego z liniami różnej długości?

### Ćwiczenie 4.5 – Wskaźniki

Dany jest kod:

```c
int a = 10;
int b = 20;
int *w = &a;
*w = 15;
w = &b;
*w = 25;
```

Podaj końcowe wartości:

```
a = ______     b = ______     na co wskazuje w? ______
```

### Ćwiczenie 4.6 – Stos i sterta

Przypisz każdą daną do właściwego obszaru pamięci (S – stos, H – sterta):

```
a)  zmienna licznikowa pętli                        ___
b)  tablica o rozmiarze podanym przez użytkownika   ___
c)  parametr przekazany do funkcji                  ___
d)  obiekt utworzony operatorem new                 ___
e)  węzeł listy wiązanej                            ___
```

### Ćwiczenie 4.7 – Błędy ze wskaźnikami

Nazwij błąd w każdym fragmencie i zaproponuj poprawkę.

```c
a)  int *w = malloc(100);
    free(w);
    *w = 5;

b)  for (int i = 0; i < 1000; i++) {
        int *t = malloc(1000);
    }

c)  int *w;
    *w = 7;
```

---

# Lekcja 5. Kolekcje: listy, kolejki, stosy, wektory

### Ćwiczenie 5.1 – Stos w działaniu

Na pustym stosie wykonano operacje. Zapisz zawartość stosu po każdej z nich oraz wartości zwracane przez `pop`.

```
push(3)  push(7)  push(1)  pop()  push(9)  pop()  pop()  push(4)
```

Jaka jest końcowa zawartość stosu, licząc od dna?

### Ćwiczenie 5.2 – Kolejka w działaniu

To samo dla kolejki:

```
enqueue(3)  enqueue(7)  enqueue(1)  dequeue()  enqueue(9)  dequeue()
```

Jaka jest końcowa zawartość kolejki, licząc od początku?

### Ćwiczenie 5.3 – Stos czy kolejka

Dobierz strukturę do zadania i uzasadnij.

| Zadanie | Struktura |
|---|---|
| Cofanie zmian w edytorze tekstu | |
| Obsługa zgłoszeń w kolejności wpływania | |
| Sprawdzanie poprawności nawiasów w wyrażeniu | |
| Drukowanie dokumentów wysłanych na drukarkę | |
| Przechodzenie po historii odwiedzonych stron | |
| Bufor odbieranych danych sieciowych | |

### Ćwiczenie 5.4 – Lista czy tablica

Dla każdego scenariusza wybierz strukturę i uzasadnij wyborem operacji, która będzie wykonywana najczęściej.

```
a)  przechowywanie 10 000 odczytów czujnika, często odczytywanych po numerze
b)  lista zadań, z której użytkownik ciągle usuwa pozycje ze środka
c)  wyniki pomiarów dopisywane wyłącznie na końcu
d)  kolejka utworów w odtwarzaczu z możliwością wstawiania w dowolne miejsce
```

### Ćwiczenie 5.5 – Złożoność

Uzupełnij tabelę symbolami O(1) albo O(n).

| Operacja | Tablica / wektor | Lista wiązana |
|---|---|---|
| Odczyt elementu nr i | | |
| Wstawienie na początek | | |
| Usunięcie znanego elementu | | |
| Wyszukiwanie wartości | | |

### Ćwiczenie 5.6 – Iterator

**a)** Czym jest iterator i jakie dwie operacje udostępnia?
**b)** Dlaczego pętla `for each` działa tak samo dla listy, zbioru i słownika?
**c)** Co się stanie, gdy podczas iteracji usuniemy element z kolekcji?
**d)** Jak poprawnie usunąć z listy wszystkie elementy spełniające warunek?

### Ćwiczenie 5.7 [K] – Sprawdzanie nawiasów

Napisz program, który sprawdza, czy w wyrażeniu poprawnie sparowano nawiasy `(`, `[` i `{`. Użyj stosu. Przetestuj na przykładach:

```
( a + [ b * c ] )        -> poprawne
{ ( a + b ]  }           -> niepoprawne
( ( a + b )              -> niepoprawne
```

---

# Lekcja 6. Projektowanie zestawu danych dla problemu programistycznego

Lekcja podsumowująca dział. Pracujemy według schematu z prezentacji:
**typ elementów → znaczenie kolejności → sposób wyszukiwania → miejsce wstawiania i usuwania.**

### Ćwiczenie 6.1 – System biblioteczny

Zaprojektuj zestaw danych dla biblioteki szkolnej. Wymagania:

- biblioteka przechowuje książki: tytuł, autor, numer inwentarzowy, rok wydania, czy wypożyczona,
- czytelnik ma imię, nazwisko, klasę i numer karty,
- najczęstsza operacja: znalezienie książki po numerze inwentarzowym,
- druga co do częstości: wypisanie wszystkich książek wypożyczonych przez czytelnika,
- historia wypożyczeń ma przetrwać zamknięcie programu.

| Dana | Struktura | Uzasadnienie |
|---|---|---|
| | | |

Wypełnij tabelę (minimum sześć pozycji) i zaznacz, które dane trafiają do pliku.

### Ćwiczenie 6.2 – Sklep internetowy

Zaprojektuj dane dla koszyka zakupowego:

- produkt: nazwa, cena, dostępna liczba sztuk,
- koszyk: lista pozycji, każda z produktem i liczbą sztuk,
- użytkownik dodaje i usuwa pozycje w dowolnym momencie,
- przy każdym wyświetleniu koszyka liczona jest wartość całkowita,
- produkty wyszukiwane są po kodzie produktu.

Zapisz projekt i odpowiedz: jakiego typu użyjesz dla ceny i dlaczego?

### Ćwiczenie 6.3 – Znajdź błąd w projekcie

Wskaż błąd i zaproponuj poprawkę.

```
a)  Dziennik ocen: tablica nazwisk, tablica ocen, tablica przedmiotów.

b)  Lista 50 000 użytkowników przeszukiwana po loginie - zwykła lista.

c)  Historia operacji w kalkulatorze z funkcją cofania - kolejka FIFO.

d)  Ceny produktów przechowywane jako liczby zmiennoprzecinkowe.

e)  Tablica statyczna na 100 pozycji dla koszyka zakupowego.
```

### Ćwiczenie 6.4 – Gra w statki

Zaprojektuj dane dla gry w statki:

**a)** Jak przechowasz planszę 10 × 10 i czym oznaczysz pole puste, statek, trafienie i pudło?
**b)** Jak przechowasz informację o statkach (rozmiar, położenie, liczba trafień)?
**c)** Jak sprawdzisz, czy statek został zatopiony?
**d)** Jak zapiszesz historię strzałów, żeby dało się ją odtworzyć po kolei?

### Ćwiczenie 6.5 – Zadanie zespołowe

W parach zaprojektujcie kompletny zestaw danych dla wybranego systemu:

- rezerwacja sal lekcyjnych,
- system zamawiania posiłków w stołówce,
- aplikacja do wypożyczalni sprzętu sportowego,
- panel zarządzania zawodami sportowymi.

Przygotujcie dokument zawierający:
1. listę danych wraz z typami prostymi,
2. definicje rekordów,
3. wybrane struktury danych z uzasadnieniem,
4. odpowiedź na pytanie, co i w jakiej postaci trafia do pliku.

Wynik prezentujecie klasie. Pozostali zadają po jednym pytaniu o konsekwencje wybranych rozwiązań.

---

## Kryteria oceny

| Kryterium | Punkty |
|---|---|
| Ćwiczenia z lekcji 1 (tablice, indeksy, macierze) | 5 |
| Ćwiczenia z lekcji 2 (tablice dynamiczne i słowniki) | 5 |
| Ćwiczenia z lekcji 3 (rekordy, rozmiary, unie) | 5 |
| Ćwiczenia z lekcji 4 (pliki i wskaźniki) | 5 |
| Ćwiczenia z lekcji 5 (kolekcje, stos, kolejka, iterator) | 5 |
| Ćwiczenia 6.1 – 6.4 (projekt danych z uzasadnieniem) | 8 |
| Ćwiczenie 6.5 (projekt zespołowy) | 2 |
| **Razem** | **35** |

Progi: 35–32 celujący · 31–27 bardzo dobry · 26–21 dobry · 20–15 dostateczny · 14–11 dopuszczający

---

# Klucz odpowiedzi

<details>
<summary>Rozwiń klucz</summary>

## Lekcja 1

**1.1** a) 0 b) 7 c) 8 d) `<` e) Java zgłasza wyjątek i zatrzymuje program; C nie sprawdza zakresu i czyta pamięć spoza tablicy, co bywa źródłem trudnych do wykrycia błędów.

**1.2** `tab[1]` = 2004, `tab[3]` = 2012, `tab[5]` = 2020. Wzór: adres = 2000 + i · 4. Cała tablica zajmuje 24 bajty.

**1.3**

```python
def srednia(tab):
    return sum(tab) / len(tab)

def indeks_najmniejszego(tab):
    idx = 0
    for i in range(1, len(tab)):
        if tab[i] < tab[idx]:
            idx = i
    return idx

def ile_wiekszych(tab, wartosc):
    licznik = 0
    for x in tab:
        if x > wartosc:
            licznik += 1
    return licznik
```

**1.4** a) Pętla powinna zaczynać się od 0 i kończyć warunkiem `i < n` – pomija pierwszy element i wychodzi poza zakres. b) Wartość początkowa powinna wynosić `tab[0]`, nie 0 – dla samych liczb ujemnych algorytm zwróci zero. c) W ostatnim przebiegu `tab[i+1]` wychodzi poza tablicę; warunek powinien brzmieć `i < n - 1`.

**1.5** a) 1 b) 7 c) 12 d) 9

```python
# e)
for w in range(3):
    print(sum(m[w]))

# f)
suma = 0
for i in range(n):
    suma += m[i][i]
```

**1.6** a) 7 8 9 1 2 3 b) 7 1 8 2 9 3 c) C stosuje układ wierszami, Fortran kolumnami.

**1.7**

```python
for w in range(8):
    linia = ""
    for k in range(8):
        linia += "#" if (w + k) % 2 == 0 else "."
    print(linia)
```

## Lekcja 2

**2.1**

| Element | Rozmiar | Pojemność | Przepisanie |
|---|---|---|---|
| 1 | 1 | 2 | nie |
| 2 | 2 | 2 | nie |
| 3 | 3 | 4 | tak |
| 5 | 5 | 8 | tak |
| 9 | 9 | 16 | tak |

**2.2** Python: `list`, `append`, `len` · Java: `ArrayList`, `add`, `size` · C++: `std::vector`, `push_back`, `size` · C#: `List<T>`, `Add`, `Count`

**2.3** Oceny w kolejności – lista (kolejność ma znaczenie) · Mieszkańcy według nazwy – słownik (szukamy po nazwie) · Kolejka zgłoszeń – kolejka FIFO · Ustawienia – słownik · Lista zakupów – lista · Liczba wystąpień słów – słownik.

**2.4**

```python
magazyn["gwozdzie"] = 200
magazyn["srubki"] += 30
"wkrety" in magazyn
del magazyn["podkladki"]
for k, v in magazyn.items():
    if v < 100: print(k, v)
sum(magazyn.values())
```

**2.5** a) tak – niezmienny i jednoznaczny b) nie – dwie osoby mogą mieć to samo imię c) nie – listę da się zmienić, więc nie nadaje się na klucz d) tak e) tak f) nie – zmiana pól zmienia skrót i wartość staje się nieosiągalna.

**2.6**

```python
licznik = {}
for slowo in zdanie.lower().split():
    licznik[slowo] = licznik.get(slowo, 0) + 1
```

Lista wymagałaby przeglądania wszystkich dotychczasowych słów przy każdym kolejnym – koszt rósłby wraz z długością tekstu.

## Lekcja 3

**3.1** Przykład: `tytul` – łańcuch · `autor` – łańcuch · `nr_inwentarzowy` – łańcuch (zera wiodące, bywa z literami) · `rok_wydania` – `int16` · `czy_wypozyczona` – `bool`.

**3.2** a) Usunięcie lub przestawienie pozycji wymaga zmiany we wszystkich tablicach; łatwo o rozjechanie danych; dodanie nowego pola oznacza kolejną tablicę. b)

```c
struct Pracownik { char nazwisko[40]; int wiek; float pensja; };
struct Pracownik firma[100];
```

c)

```c
for (int i = 0; i < n; i++)
    if (firma[i].pensja > 5000) printf("%s\n", firma[i].nazwisko);
```

**3.3** a) 8 b) 8 c) 8 d) 8. W podpunkcie `b` po polu `char` kompilator wstawia 3 bajty wypełnienia, żeby pole `int` zaczynało się pod adresem podzielnym przez 4.

**3.4**

```c
struct Adres { char ulica[50]; char miasto[30]; char kod[7]; };
struct Data  { int dzien; int miesiac; int rok; };
struct Klient { char nazwa[60]; struct Adres adres; };
struct Zamowienie {
    int numer;
    struct Klient klient;
    struct Data data;
    double wartosc;
};
```

Odwołanie: `z.klient.adres.miasto`

**3.5** a) Struktura ma rozmiar równy sumie pól powiększonej o wypełnienie, unia – rozmiar największego pola. b) Jedno. c) Bez niego program nie wie, które pole unii zostało zapisane, więc nie potrafi poprawnie odczytać zawartości. d) Oszczędność pamięci w urządzeniach wbudowanych albo odczyt tych samych bajtów na kilka sposobów, na przykład przy obsłudze protokołów sieciowych.

**3.6**

```c
enum Rodzaj { CALKOWITY, RZECZYWISTY, BLAD };

struct Pomiar {
    enum Rodzaj rodzaj;
    union {
        int    calkowity;
        double rzeczywisty;
        char   komunikat[40];
    } wartosc;
};

if (p.rodzaj == CALKOWITY)        printf("%d", p.wartosc.calkowity);
else if (p.rodzaj == RZECZYWISTY) printf("%f", p.wartosc.rzeczywisty);
else                              printf("%s", p.wartosc.komunikat);
```

## Lekcja 4

**4.1** Wczytanie listy – `r` · Zapis raportu od nowa – `w` · Dopisanie wpisu – `a` · Odczyt zdjęcia – `rb`

**4.2** a) T b) B c) T d) B e) T

**4.3**

```python
oceny = [5, 4, 3, 5, 4]
with open("oceny.txt", "w") as f:
    for o in oceny:
        f.write(f"{o}\n")

with open("oceny.txt", "r") as f:
    wczytane = [int(l) for l in f if l.strip()]
srednia = sum(wczytane) / len(wczytane)

with open("oceny.txt", "a") as f:        # tryb dopisywania, nie zapisu
    f.write(f"srednia: {srednia:.2f}\n")
```

**4.4** a) 0 b) 320 c) i · 64 d) 320 rekordów. e) Linie mają różną długość, więc nie da się wyliczyć pozycji n-tej linii bez przeczytania wszystkich poprzednich.

**4.5** `a` = 15, `b` = 25, wskaźnik `w` wskazuje na zmienną `b`.

**4.6** a) S b) H c) S d) H e) H

**4.7** a) Wskaźnik wiszący – obszar został już zwolniony; nie wolno z niego korzystać, a po `free` warto przypisać wskaźnikowi wartość pustą. b) Wyciek pamięci – w każdym obrocie pętli rezerwujemy 1000 bajtów i nigdy ich nie zwalniamy; należy dodać `free(t)`. c) Wskaźnik niezainicjowany – wskazuje przypadkowy adres; trzeba najpierw przypisać mu adres istniejącej zmiennej albo zarezerwowaną pamięć.

## Lekcja 5

**5.1**

| Operacja | Zawartość (od dna) | Zwrócono |
|---|---|---|
| push(3) | 3 | |
| push(7) | 3, 7 | |
| push(1) | 3, 7, 1 | |
| pop() | 3, 7 | 1 |
| push(9) | 3, 7, 9 | |
| pop() | 3, 7 | 9 |
| pop() | 3 | 7 |
| push(4) | 3, 4 | |

Końcowa zawartość: 3, 4.

**5.2** Kolejno zdejmowane są 3 i 7. Końcowa zawartość od początku: 1, 9.

**5.3** Cofanie zmian – stos · Zgłoszenia – kolejka · Nawiasy – stos · Drukowanie – kolejka · Historia stron – stos (dwa stosy) · Bufor sieciowy – kolejka.

**5.4** a) Tablica lub wektor – dominuje odczyt po numerze. b) Lista wiązana – częste usuwanie ze środka. c) Wektor – dopisywanie wyłącznie na końcu ma stały koszt zamortyzowany. d) Lista wiązana – wstawianie w dowolne miejsce.

**5.5**

| Operacja | Tablica | Lista |
|---|---|---|
| Odczyt elementu nr i | O(1) | O(n) |
| Wstawienie na początek | O(n) | O(1) |
| Usunięcie znanego elementu | O(n) | O(1) |
| Wyszukiwanie wartości | O(n) | O(n) |

**5.6** a) Iterator to obiekt dający jednolity sposób przeglądania kolekcji; udostępnia sprawdzenie, czy jest następny element, oraz pobranie następnego elementu. b) Bo każda z tych kolekcji dostarcza własny iterator, a pętla korzysta wyłącznie z dwóch wymienionych operacji. c) Iterator zostaje unieważniony – program zgłasza błąd albo pomija elementy. d) Zbudować nową kolekcję zawierającą wyłącznie elementy, które mają zostać, albo iterować po kopii.

**5.7**

```python
def sprawdz(wyrazenie):
    pary = {")": "(", "]": "[", "}": "{"}
    stos = []
    for znak in wyrazenie:
        if znak in "([{":
            stos.append(znak)
        elif znak in pary:
            if not stos or stos.pop() != pary[znak]:
                return False
    return len(stos) == 0
```

## Lekcja 6

**6.1** Przykładowy projekt: rekord `Ksiazka` (tytuł, autor, numer inwentarzowy, rok, czy wypożyczona) · rekord `Czytelnik` (imię, nazwisko, klasa, numer karty) · zbiór książek jako **słownik** z kluczem będącym numerem inwentarzowym, bo to najczęstsza operacja wyszukiwania · wypożyczenia jako **słownik**: numer karty czytelnika prowadzi do listy numerów książek · historia wypożyczeń zapisywana do **pliku tekstowego** w trybie dopisywania, bo ma przetrwać zamknięcie programu.

**6.2** Produkt jako rekord, katalog produktów jako słownik z kluczem będącym kodem produktu, koszyk jako wektor pozycji (rekord: produkt i liczba sztuk). Cena jako typ dziesiętny albo liczba całkowita groszy – liczba zmiennoprzecinkowa powoduje błędy zaokrągleń w rozliczeniach.

**6.3** a) Tablice równoległe – zamienić na tablicę rekordów. b) Przeszukiwanie listy po loginie ma koszt liniowy – użyć słownika z kluczem będącym loginem. c) Cofanie wymaga dostępu do ostatniej operacji, więc właściwy jest stos, nie kolejka. d) Kwoty na liczbach zmiennoprzecinkowych – użyć typu dziesiętnego lub groszy jako liczb całkowitych. e) Stały rozmiar koszyka – użyć tablicy dynamicznej.

**6.4** a) Tablica dwuwymiarowa 10 × 10 wartości znakowych albo całkowitych, na przykład 0 – puste, 1 – statek, 2 – trafienie, 3 – pudło. b) Rekord `Statek` (rozmiar, lista pól, liczba trafień), statki w wektorze. c) Statek jest zatopiony, gdy liczba trafień zrówna się z jego rozmiarem. d) Historia strzałów jako lista lub wektor par współrzędnych – kolejność ma znaczenie i dopisujemy wyłącznie na końcu.

</details>

---

## Materiały uzupełniające

- Prezentacja do działu: `03-struktury-danych.pdf`
- Materiały z działu I (typy proste): `02-typy-danych-cwiczenia.md`
- Konsola Pythona do sprawdzania przykładów na bieżąco
