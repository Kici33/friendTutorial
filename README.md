# Programming Tutorial 2022

**Typy Danych**

w Javie wyróżniamy takie rzeczy,
jak typy danych. Służą one,
aby zakomunikować komputerowi 
jakie dane będziemy przechowywać.
Przykłady:


`String` - "Tekst" -> Zapisywany pomiędzy dwoma cudzysłowami (")
`int/Integer` - 5 -> Liczba
`boolean` -> Zmienna 0/1 (true/false)
`float/double/long` -> Liczby zmiennoprzecinkowe (0.5, 1.25F etc.)
`void` -> Nic (brak zwracanej wartości etc.)

---

**Modyfikatory dostępu**
w Javie wyróżniamy 3 typy dostępu do rzeczy (klas/metod/zmiennych). Służą one aby ograniczyć dostęp do rzeczy (bądź aby uniemożliwiać pewne operacje, które omówimy później).

`public` -> Najprostszy typ, ponieważ umożliwia on dostęp ze wszystkich miejsc (innych klas etc.)
`protected` -> Typ który ogranicza dostęp tylko do
klas wewnątrz tego samego **package'a** (package możemy traktować jak swego rodzaju folder, w którym są składowane wszystkie klasy).
`private` -> Typ prosty, który umożliwia dostęp do rzeczy tylko z klasy w której jest zadeklarowane (nie można uzyskać dostępu z zewnątrz)

---

**Atrybut static**

Atrybut static służy do tego aby dać **bezpośredni** dostęp do rzeczy bez uzyskania czegoś takiego jak instancja danej klasy (o tym później)

---

**Zapis Zmiennych**

Przechodzimy do pierwszej rzeczy, którą trzeba zapamiętać na życie, chodzi o składnię tego jak deklarujemy zmienne, a zatem:

> na początku deklarujemy:
1. modyfikator dostępu (w zależności od kontekstu)
2. atrybut <static> (opcjonalnie)
3. typ danych

W tej kolejności (zawsze)
Dla przykładu:

`public static int liczba = 5;`
`String test = "dziala";`
`protected boolean rozumiesz = false;`




