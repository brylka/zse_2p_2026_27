# Typy danych – ćwiczenia

**Projektowanie oprogramowania | Technik programista | Klasa II**
Dział I: Typy danych w projektowaniu aplikacji
Efekty kształcenia: **INF.04.3.1**, **INF.04.3.2**
Opracował: **Bartosz Bryniarski**

---

## Jak korzystać z tego materiału

Ćwiczenia są przypisane do sześciu lekcji działu. Zadania oznaczone **[K]** można wykonać na komputerze (Python w konsoli, dowolne IDE), pozostałe rozwiązuje się na kartce.

Klucz odpowiedzi znajduje się na końcu pliku.

| Lekcja | Temat | Ćwiczenia |
|---|---|---|
| 1 | Rola typów danych. Typowanie statyczne i dynamiczne | 1.1 – 1.5 |
| 2 | Typy liczbowe stałoprzecinkowe | 2.1 – 2.6 |
| 3 | Typy zmiennoprzecinkowe | 3.1 – 3.6 |
| 4 | Typ logiczny i znakowy. Kodowanie znaków | 4.1 – 4.7 |
| 5 | Typ łańcuchowy | 5.1 – 5.6 |
| 6 | Dobór typu prostego do problemu programistycznego | 6.1 – 6.5 |

---

# Lekcja 1. Rola typów danych. Typowanie statyczne i dynamiczne

### Ćwiczenie 1.1 – Trzy cechy typu

Dla każdego typu wypełnij tabelę.

| Typ | Przykładowe wartości | Dozwolone operacje | Rozmiar w pamięci |
|---|---|---|---|
| `bool` | | | |
| `int32` | | | |
| `char` | | | |

### Ćwiczenie 1.2 – Statyczne czy dynamiczne

Przy każdym fragmencie napisz, czy język stosuje typowanie **statyczne** czy **dynamiczne**, i uzasadnij jednym zdaniem.

```
a)  int x = 5;  x = "tekst";      → błąd przy kompilacji
b)  x = 5;      x = "tekst"       → działa poprawnie
c)  auto y = 3.14;                → y jest typu double
d)  let z = 10; z = "dziesięć";   → działa w JavaScripcie
```

### Ćwiczenie 1.3 – Silne czy słabe

Rozstrzygnij, co zwróci każde wyrażenie. Jeśli będzie to błąd – napisz „błąd".

| Wyrażenie | Python | JavaScript |
|---|---|---|
| `"5" + 3` | | |
| `"5" * 2` | | |
| `"10" - 5` | | |
| `True + 1` | | |

### Ćwiczenie 1.4 – Konwersje

Podaj wynik każdej konwersji.

```
a)  (int) 7.99            = ______
b)  (int) -7.99           = ______
c)  (double) 5            = ______
d)  (int) 3.5 + (int) 3.5 = ______
e)  (int)(3.5 + 3.5)      = ______
```

Wyjaśnij, dlaczego wyniki `d` i `e` się różnią.

### Ćwiczenie 1.5 [K] – Sprawdź w konsoli

W konsoli Pythona wykonaj:

```python
print(type(5), type(5.0), type("5"), type(True))
print(int("42") + 8)
print(int("42abc"))
```

Zapisz, jaki wyjątek zwraca ostatnia linia i co on oznacza.

---

# Lekcja 2. Typy liczbowe stałoprzecinkowe

### Ćwiczenie 2.1 – Zakresy

Uzupełnij tabelę. Wartości zapisz w postaci liczbowej, nie wzorem.

| Liczba bitów | Liczba wartości | Zakres bez znaku | Zakres ze znakiem |
|---|---|---|---|
| 4 | | | |
| 8 | | | |
| 16 | | | |

### Ćwiczenie 2.2 – Konwersja dwójkowo-dziesiętna

Zamień na system dziesiętny (liczby bez znaku):

```
a)  0000 1111  = ______
b)  1000 0000  = ______
c)  1111 1111  = ______
```

A teraz te same bajty odczytane jako liczby **ze znakiem** w kodzie U2:

```
a)  0000 1111  = ______
b)  1000 0000  = ______
c)  1111 1111  = ______
```

### Ćwiczenie 2.3 – Przepełnienie

Zmienna typu `int8` (zakres −128 … 127) ma wartość 120. Program dodaje do niej 10 w pętli. Wypisz kolejne wartości:

```
120 → ______ → ______ → ______
```

Po ilu krokach wartość stanie się ujemna?

### Ćwiczenie 2.4 – Dzielenie całkowite

Podaj wyniki:

```
a)  17 / 5    (liczby całkowite)  = ______
b)  17 % 5                        = ______
c)  -17 / 5   (liczby całkowite)  = ______
d)  Ile stron po 20 rekordów potrzeba na 143 rekordy?  = ______
```

Zapisz wzór ogólny na liczbę stron przy `n` rekordach i `k` rekordach na stronie.

### Ćwiczenie 2.5 – Dobór typu

Dla każdej danej dobierz najmniejszy wystarczający typ całkowity i uzasadnij.

| Dana | Typ | Uzasadnienie |
|---|---|---|
| Wiek człowieka | | |
| Rok kalendarzowy | | |
| Liczba mieszkańców Polski | | |
| Liczba mieszkańców Ziemi | | |
| Liczba bajtów pliku wideo | | |
| Temperatura w °C (całkowita) | | |

### Ćwiczenie 2.6 [K] – Przepełnienie na własne oczy

W Pythonie zainstalowany jest moduł `numpy`, który używa typów o stałym rozmiarze:

```python
import numpy as np
x = np.int8(127)
print(x + np.int8(1))
```

Zapisz wynik i wyjaśnij go w dwóch zdaniach.

---

# Lekcja 3. Typy zmiennoprzecinkowe

### Ćwiczenie 3.1 – float czy double

| Zastosowanie | float czy double | Dlaczego |
|---|---|---|
| Współrzędne GPS z dokładnością do metra | | |
| Kolor piksela (0.0 – 1.0) | | |
| Obliczenia naukowe, całkowanie numeryczne | | |
| Saldo konta bankowego | | |

### Ćwiczenie 3.2 – Zapisywalne czy nie

Zaznacz, które liczby da się zapisać **dokładnie** w systemie dwójkowym:

```
0,5     0,1     0,25     0,3     0,75     0,125     0,2     1,5
```

Podaj regułę, według której rozstrzygasz.

### Ćwiczenie 3.3 [K] – Klasyczny przykład

Wykonaj w konsoli:

```python
print(0.1 + 0.2)
print(0.1 + 0.2 == 0.3)
print(f"{0.1:.20f}")
print(0.1 + 0.7)
```

Zapisz wyniki. Który z nich Cię zaskoczył?

### Ćwiczenie 3.4 – Poprawa kodu

Poniższa funkcja czasem zwraca błędny wynik. Znajdź przyczynę i popraw kod.

```python
def czy_zaplacono(kwota_wplacona, kwota_do_zaplaty):
    if kwota_wplacona == kwota_do_zaplaty:
        return True
    return False
```

### Ćwiczenie 3.5 – Wartości specjalne

Podaj wynik każdego wyrażenia: liczba, `inf`, `-inf`, `nan` albo błąd.

```
a)  1.0 / 0.0        = ______
b)  -1.0 / 0.0       = ______
c)  0.0 / 0.0        = ______
d)  1 / 0            = ______   (liczby całkowite)
e)  float('inf') - float('inf')  = ______
f)  float('nan') == float('nan') = ______
```

### Ćwiczenie 3.6 – Kwoty pieniężne

Sklep internetowy przechowuje ceny jako `float`. Klient kupuje 3 sztuki towaru po 19,99 zł.

**a)** Jaka kwota może pojawić się w systemie zamiast 59,97?
**b)** Zaproponuj dwa różne poprawne rozwiązania.
**c)** Jaki typ kolumny wybierzesz w bazie danych dla ceny? Podaj pełny zapis.

---

# Lekcja 4. Typ logiczny i znakowy. Kodowanie znaków

### Ćwiczenie 4.1 – Tablica prawdy

Wypełnij:

| a | b | `a AND b` | `a OR b` | `NOT a` | `a XOR b` | `NOT (a AND b)` |
|---|---|---|---|---|---|---|
| F | F | | | | | |
| F | T | | | | | |
| T | F | | | | | |
| T | T | | | | | |

### Ćwiczenie 4.2 – Skrócone obliczanie

```java
if (lista != null && lista.size() > 0) { ... }
```

**a)** Co się stanie, gdy `lista` jest pusta (`null`)?
**b)** Co się stanie po zamianie warunków miejscami?
**c)** Zapisz analogiczny warunek z operatorem `||`.

### Ćwiczenie 4.3 – Kody znaków

Uzupełnij, korzystając z tego, że `'A'` = 65, `'a'` = 97, `'0'` = 48:

```
a)  kod znaku 'D'          = ______
b)  kod znaku 'z'          = ______
c)  znak o kodzie 74       = ______
d)  '7' - '0'              = ______
e)  (char)('a' - 32)       = ______
```

### Ćwiczenie 4.4 – Zamiana wielkości liter

Napisz w pseudokodzie funkcję, która zamienia wielką literę na małą, korzystając wyłącznie z arytmetyki na kodach znaków. Uwzględnij sprawdzenie, czy znak faktycznie jest wielką literą.

### Ćwiczenie 4.5 – ASCII a Unicode

Rozstrzygnij, czy zdanie jest prawdziwe (P) czy fałszywe (F):

```
a)  ASCII koduje znaki na 8 bitach.                          ___
b)  Unicode to sposób zapisu znaków w bajtach.               ___
c)  UTF-8 jest zgodne wstecz z ASCII.                        ___
d)  W UTF-8 każdy znak zajmuje dokładnie 2 bajty.            ___
e)  U+0041 to punkt kodowy litery A.                         ___
f)  Emoji nie da się zapisać w UTF-8.                        ___
```

Popraw zdania fałszywe.

### Ćwiczenie 4.6 – Mojibake

Uczeń zapisał plik w kodowaniu Windows-1250, a otworzył go w edytorze ustawionym na UTF-8.

**a)** Jak nazywa się to zjawisko?
**b)** Czy dane w pliku zostały uszkodzone? Uzasadnij.
**c)** Wymień trzy miejsca w projekcie webowym, w których trzeba ustawić kodowanie.

### Ćwiczenie 4.7 [K] – Bajty w praktyce

```python
for tekst in ["Ala", "Zażółć", "cześć 😀"]:
    print(tekst, len(tekst), len(tekst.encode("utf-8")))
```

Wypełnij tabelę i wyjaśnij różnice.

| Tekst | Liczba znaków | Liczba bajtów |
|---|---|---|
| `Ala` | | |
| `Zażółć` | | |
| `cześć 😀` | | |

---

# Lekcja 5. Typ łańcuchowy

### Ćwiczenie 5.1 – Indeksowanie

Dla napisu `s = "Programista"` podaj wynik:

```
a)  len(s)      = ______
b)  s[0]        = ______
c)  s[3]        = ______
d)  s[-1]       = ______
e)  s[0:6]      = ______
f)  s.find("m") = ______
```

### Ćwiczenie 5.2 – Niemutowalność

```python
tekst = "kot"
tekst[0] = "b"
```

**a)** Co się stanie po uruchomieniu tego kodu w Pythonie?
**b)** Zapisz poprawną wersję dającą napis `"bot"`.
**c)** Ile obiektów typu `str` istnieje po wykonaniu poprawnej wersji?

### Ćwiczenie 5.3 – Reprezentacja w pamięci

Narysuj zawartość pamięci dla napisu `"Ala"`:

**a)** w konwencji języka C (zakończenie bajtem zerowym),
**b)** w konwencji z zapisaną długością.

Która wersja szybciej odpowiada na pytanie o długość napisu? Dlaczego?

### Ćwiczenie 5.4 – Wydajność

```python
wynik = ""
for i in range(100000):
    wynik += str(i)
```

**a)** Dlaczego ten kod działa wolno?
**b)** Zapisz wersję szybszą.
**c)** Jak nazywa się odpowiednik tego rozwiązania w Javie?

### Ćwiczenie 5.5 – Parsowanie danych

Dany jest wiersz z pliku CSV:

```
  Kowalski;Jan;2008-05-14;klasa 2p  
```

Napisz w pseudokodzie lub w Pythonie ciąg operacji, który:
1. usunie białe znaki z początku i końca,
2. podzieli wiersz na pola,
3. wypisze samo nazwisko i rok urodzenia.

### Ćwiczenie 5.6 – Porównywanie

Uporządkuj rosnąco według **kodów znaków** (tak jak zrobi to komputer):

```
"banan"   "Banan"   "Ananas"   "ananas"   "Żaba"   "zebra"
```

Czy wynik jest zgodny z porządkiem alfabetycznym języka polskiego? Co trzeba zastosować, żeby był?

---

# Lekcja 6. Dobór typu prostego do problemu programistycznego

To zajęcia podsumowujące cały dział. Pracujemy według schematu z lekcji 2:
**czy może być ujemna → jaka jest wartość maksymalna → jaki zapas → jaki kontekst.**

### Ćwiczenie 6.1 – Formularz rejestracyjny

Projektujesz formularz rejestracji do serwisu. Dobierz typ dla każdego pola i uzasadnij wybór w jednym zdaniu.

| Pole | Typ | Uzasadnienie |
|---|---|---|
| Imię | | |
| Wiek | | |
| PESEL | | |
| Numer telefonu | | |
| Adres e-mail | | |
| Zgoda na regulamin | | |
| Wzrost w cm | | |
| Waga w kg (z dokładnością do 0,1) | | |

> **Wskazówka:** przy dwóch polach z tej listy odruchowy wybór typu liczbowego jest błędny. Zastanów się, czy na tych danych wykonuje się kiedykolwiek działania arytmetyczne.

### Ćwiczenie 6.2 – Sklep internetowy

Zaprojektuj typy dla tabeli `zamowienie`:

| Kolumna | Typ w aplikacji | Typ w bazie danych | Uzasadnienie |
|---|---|---|---|
| `id_zamowienia` | | | |
| `id_klienta` | | | |
| `data_zlozenia` | | | |
| `wartosc_brutto` | | | |
| `liczba_pozycji` | | | |
| `czy_oplacone` | | | |
| `kod_rabatowy` | | | |

### Ćwiczenie 6.3 – Znajdź błąd

W każdym przypadku wskaż błąd w doborze typu i zaproponuj poprawkę.

```
a)  float saldo_konta;
b)  int numer_telefonu = 501234567;
c)  byte liczba_uczniow_w_szkole;
d)  int identyfikator_uzytkownika;   // portal społecznościowy
e)  char plec;                        // wartości 'K' lub 'M'
f)  int kod_pocztowy = 50137;         // dla kodu 50-137
```

### Ćwiczenie 6.4 – Sensor temperatury

Projektujesz oprogramowanie stacji pogodowej. Czujnik mierzy temperaturę w zakresie od −40 °C do +85 °C z dokładnością 0,1 °C, a odczyt zapisywany jest co minutę przez cały rok.

**a)** Jaki typ wybierzesz dla pojedynczego odczytu? Rozważ co najmniej dwa warianty.
**b)** Ile odczytów powstanie w ciągu roku?
**c)** Ile pamięci zajmą wszystkie odczyty przy każdym z rozważanych typów?
**d)** Zaproponuj rozwiązanie oszczędzające pamięć bez utraty dokładności.

### Ćwiczenie 6.5 – Zadanie zespołowe

W parach zaprojektujcie zestaw typów dla wybranego systemu:

- dziennik elektroniczny (oceny, frekwencja, uczniowie),
- system biblioteczny (książki, wypożyczenia, czytelnicy),
- sklep z biletami na koncerty,
- aplikacja do śledzenia treningów.

Przygotujcie tabelę z kolumnami: **nazwa danej · typ · zakres wartości · uzasadnienie**. Minimum 10 pozycji. Wynik prezentujecie klasie.

---

## Materiały uzupełniające

- Prezentacja do działu: `02-typy-danych.pdf`
- Tablica kodów ASCII – dowolne wydanie podręcznikowe
- Konsola Pythona do sprawdzania przykładów na bieżąco
