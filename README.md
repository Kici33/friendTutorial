# Programming Tutorial 2022

**Typy Danych (data types)**

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

**Modyfikatory dostępu (access modifiers)**
w Javie wyróżniamy 3 typy dostępu do rzeczy (klas/metod/zmiennych). Służą one aby ograniczyć dostęp do rzeczy (bądź aby uniemożliwiać pewne operacje, które omówimy później).

`public` -> Najprostszy typ, ponieważ umożliwia on dostęp ze wszystkich miejsc (innych klas etc.)
`protected` -> Typ który ogranicza dostęp tylko do
klas wewnątrz tego samego **package'a** (package możemy traktować jak swego rodzaju folder, w którym są składowane wszystkie klasy).
`private` -> Typ prosty, który umożliwia dostęp do rzeczy tylko z klasy w której jest zadeklarowane (nie można uzyskać dostępu z zewnątrz)

---

**Atrybut static**

Atrybut static służy do tego aby dać **bezpośredni** dostęp do rzeczy bez uzyskania czegoś takiego jak instancja danej klasy (o tym później)

---

**Zapis Zmiennych (Variables)**

Przechodzimy do pierwszej rzeczy, którą trzeba zapamiętać na życie, chodzi o składnię tego jak deklarujemy zmienne, a zatem:

> na początku deklarujemy:
1. modyfikator dostępu (w zależności od kontekstu (opcjonalne))
2. atrybut `static` (opcjonalnie)
3. typ danych

W tej kolejności (zawsze)
Dla przykładu:

`public static int liczba = 5;`
`String test = "dziala";`
`protected boolean rozumiesz = false;`

---

**Final w zmiennych (Status Immutable)**

w Javie wszystkie zmienne możemy tworzyć z kluczem `final`, który nadaje im status `immutable`, który oznacza, że nie da się ich edytować po zadeklarowaniu). W praktyce:
```java
public final int i = 5; 

i = 10; <- Tutaj pojawi się błąd z tej racji, że próbujemy zmienić wartość i podczas, gdy jest ona immutable

```

W innym przypadku, zwykłe podanie nazwy zmiennej oraz znaku równości by przypisać coś do zmiennej pozwoli nam nadpisać wartość (zapamiętać, że nie trzeba już podawać typu bo `odwołujemy` się a nie `deklarujemy`).

---

**Operacje na zmiennych**

Jak już zobaczyliście, zmiennym nadajemy wartość poprzez użycie znaku
równa się (1-krotnego), który powoduje nadpisanie wartości.

Natomiast w Javie występują również sytuacje, które ułatwiają bardzo życie za sprawą dedykowanej symboliki dla dodawania/mnożenia/dzielenia/odejmowania.
Ale najłatwiej jest zrozumieć z takiego przykładu poniżej

```java
public int start = 5; // Startowa wartość (liczba 5)

start += 50; // Dodanie do start wartości 50 (zapis +=)
start -= 50; // Odjęcie od start wartości 50 (zapis -=)
start *= 10; // Pomnożenie o 10 razy (w rezultacie 5*10 zapis *=)
start /= 10; // Podzielenie o 10 razy (w rezultacie 50/10 = 5)

/**
    Dla kontekstu, jeżeli ktoś by nie rozumiał dlaczego, na końcu jest 50/10. Wynika to z tego, że jak wykonujemy te operację jedna po drugiej, to *= 10 nadaje zmiennej start wartość 50, od której później dzielimy oraz każda z tych instrukcji bazuje na wyniku poprzedniej
*/

```
Trzeba pamiętać o tym, że nie każdy typ danych obsługuje tego typu zapis za sprawą tego, że np. do zmiennej `boolean` (tak/nie - true/false), nie możliwym by było dodawanie wartości czy jej dzielenie.

---

**Funkcje**

Funkcje to bloki, w których kod wykonywany jest linijka, po linijce (zazwyczaj, do czasu robienia rzeczy na wątkach. Ale o tym kiedy indziej).
Natomiast mając tą wiedzę trzeba zapamiętać, że kod nie może od tak po prostu `być`, ale musi istnieć wokół jakiś zasad.

Także może najlepszym przykładem byłoby po prostu pokazać jak to wygląda i wytłumaczyć, zatem:

```java
public static void main(String[] args) {
    System.out.println("Hello World!");
}
```
Kod znany wszystkim, którzy uczyli się programować czyli najprostszy program, który wyświetla słynne określenie `Hello, World!`.

Natomiast jak możecie zauważyć instrukcja odnośnie wyświetlania tego
zamknięta jest w funkcji która wygląda następująco:

```java
public static void main(String[] args) { /*code*/ }
               ^               ^            
               |     ^         |          
               void  | oznacza typ danych zwracanych
                     |         |
                     main - oznacza nazwę funkcji ale o tym poniżej
                               |
                              (String[] args) - Argumenty funkcji  
```                          

Nazwa tej funkcji jest sczególnie ważna, bo tak jak w naszym kodzie możemy nazwać funkcję jakkolwiek chcemy. Tak aby skorzystać z tego, że Java aby wykrywała nasz program jako wykonywalny szuka w poszukiwaniu funkcji o tej sczególnej nazwie.

`Argumenty funkcji` - Argumenty funkcji to wszystkie rzeczy, które będziemy chcieli przetworzyć w danej funkcji.

W funkcji `main` używane jest to aby przekazać wszystkie parametry programu (gdy się go odpala), aby np. wykonać pewne modyfikację co do jego działania.

Natomiast przykładowo, gdybyśmy chcieli stworzyć funkcję, która przykładowo bierze liczbę oraz potęgę, do której byśmy chcieli podnieść liczbę, tak nasza funkcja wyglądała by w taki sposób (+/-)

```java

public static int potegaLiczby(int liczba, int potega) {
    
    // Tutaj w zależności od tego jak dużo siedzimy w javie, tak dużo implementacji moglibyśmy znaleźć ale z racji, że nie chcę aby wam główka parowała to skupimy się na tej najprostszej a jakieś bardziej zaawansowane podam wam kiedy indziej 😎

    return liczba ** potega;

    //Operacja ** oznacza podniesienie lewej strony do potęgi z prawej strony. Warto zapamiętać aby nie męczyć.
    //Również w Javie występuje klasa Math która pozwala nam wykonywać takie operację, ale wytłumaczę wam tą klasę dokładniej później oraz częste rzeczy, których ja używam i prawdopodobnie z których i wy będziecie w miarę regularnie korzystać

    //return Math.pow(liczba, potega); <- Math.pow - Power (potęga)
}
```
