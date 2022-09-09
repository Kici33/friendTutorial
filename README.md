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

---

**Obiekty**

Wyobraźcie sobie sytuację, w której chcielibyście posiadać wiele różnych natomiast wspólnych rzeczy np. smartfonów.

Do takich oraz innych rzeczy przydają się obiekty, czyli klasy których struktura została stworzona w taki sposób, aby występywała w nich instancyjność.

Mówiąc prościej, możemy posiadać klasę "Phone" oraz mieć rózne właściwości w niej w zależności od instancji na której działamy

```java

public class Phone {

    /*
        Tutaj deklarujemy rzeczy, które nasz obiekt będzie przechowywał
    */
    private String model; 
    private int price;

    /*
        To jest konstruktor,
        jak możecie zobaczyć jego nazwa pokrywa się z nazwą klasy.
        Nie jest to przypadkowe, a identyfikuje, że jest to konstruktor klasy.
        Wykonuje się on w momencie kiedy wywołujemy nową instancję klasy
        (new Phone(data));
    */
    public Phone(String model, int price) {
        this.model = model;
        this.price = price;
    }

    /*
        Tutaj poniżej deklarujemy wszystkie punkty dostępowe do naszych danych.
        Jak możecie zobaczyć powyżej użyłem modyfikatora dostępowego private.

        Jest to z tej racji, że nie chcemy zazwyczaj dawać bezpośredniego dostępu do nadpisywania danych, ponieważ potrafi to czasami zepsuć logikę a także wywołać błędu pokroju ConcurrentModificationException co jak możemy domyślać się po nazwie występuje w przypadku kilkukrotnej modyfikacji danych w tym samym momencie.
    */

    /*
        Przykład gettera (funkcji, która ma za zadanie zwrócić nam przetrzymywane dane w zmiennej model)
    */
    public String getModel() {
        return this.model;
    }
    /*
        Przykład settera (funkcji, która za zadanie ma aby nadać nową wartość)
    */
    public void setModel(String model) {
        this.model = model;
    }
}
```

W IntellIJ występuje funkcja aby auto-generować konstruktory oraz settery oraz gettery. W tym celu używamy skrótu **Alt+Ins**

---

**Używanie funkcji statycznych oraz niestatycznych w innych klasach.**

W przypadku, gdybyśmy chcieli używać metod zadeklarowanych w innej klasie, tak referujemy się do nich za pomocą bezpośredniej instrukcji (przy funkcjach statycznych) np.

```java
MojaKlasa.mojaFunkcja();
```

Bądź w przypadku funkcji niestatycznych musimy posiadać instancję danej klasy do której referujemy


```java
MojaKlasa klasa = new MojaKlasa();
klasa.mojaFunkcja();
```

---

**Warunki IF**

Kiedy tworzymy programy zawsze musimy patrzeć na różne sposoby ich użycia (a dokładniej wszystkie możliwe).

Niezależnie czy będziemy chcieli sprawdzać, czy użytkownik ma dostęp do danej funkcji czy też coś innego natrafimy na zapis w takiej oto postaci

```java

if(boolean) {
    //code
}

```

Jak widzicie zapis samego warunku nie jest niczym ciężkim natomiast co jest w tym ciężkiego na początku to jest fakt, jak sformułować warunek, który zaplanowaliśmy sobie w głowie.

W tym miejscu nasz 
```java 
boolean
```
musi przyjąć jakąś postać, poniżej pokażę wam kilka rzeczy jak można tworzyć porównania

```java

//Porównanie tekstu

String str = "Tekst";
String str2 = "Tekst";

str.equals(str2); // zwróci True - Ten warunek sprawdza czy tekst jest dokładnie taki sam (włączając w to wielkość liter.)
str.equalsIgnoreCase(str2); // zwróci True w momencie kiedy tekst będzie się zgadzał natomiast nie zwróci uwagi na wielkość liter w tekście

int number = 1;
int otherNumber = 5;

number == otherNumber; // zwróci False z racji, że numery się zgadzają.

//Natomiast jeżeli sami stworzyliśmy sobie funkcję która zwraca boolean (przykładowo)

public boolean canRun() {
    if(user.role.has('ADMIN')) return true;
    return false;
}

//to możemy wtedy użyć zapisu

if(canRun()) 

//który automatycznie bazując na warunkach z funkcji powyżej (wymyślonych) zwróciłby wartość true bądź false
```

W javie oprócz prostego warunku `if`, występują również bloki `else if` oraż `else`.

Bloki te służą w momencie gdy chcemy dodać kolejne warunki po tym już ówcześnie sprawdzonym.

```java
if(i == 5) {

}
else if (i == 10) {

}
else {

}
```

Bloki te występują tylko w tej kolejności, natomiast może być wiele warunków `else if` położonych jeden pod drugim.

Jak będę z wami robił jakieś rzeczy etc.
to w zależności od tego co będziemy robić będziecie mogli zobaczyć, że stosuje czasami tylko `ify`.

Wynikać to będzie głównie z faktu, że jak się zastanowimy to w wielu przypadkach dzieje się tak, że na podstawie pewnych warunków będziemy wykonywać kod przypisany w danym bloku oraz nic więcej. A wtedy można zrobić coś takiego jak:

```java

//To zostaje po staremu jako jeden warunek
if(i == 5) {
    //code;
    return; //Zamykając funkcję w tym momencie powodujemy, że kod nie będzie szedł dalej (poza ifa).
}
if(i == 10) {
    //Kod dojdzie tu tylko jeżeli nie spełnił się 1 warunek (w innym przypadku funkcja by się zamknęła za sprawą returna postawionego wyżej)
    return;
}
//Gdyby się zastanowić else oznacza, że w każdym przypadku niespełnionym przez inne warunki czyli w momencie kiedy żaden z poprzednich warunków nie spełni kryteriów by wyegzekwować się.
//Oznacza to również, że jeżeli zamkniemy poprzednie bloki to jakikolwiek kod wrzucony tutaj, będzie wykonany w przypadku gdy oba nie zostały spełnione.
```

---

**Pętla For**

Pętla for jest używana w momencie kiedy chcemy wykonać blok kodu wiele razy bądź dla każdej wartości z osobna (np. dla każdego użytkownika z listy).

```java

int x = 10;

for(int i = 0; i < x; i++) {
    //code
}

// W bloku powyżej jak widzicie jest zrobiona pętla, która będzie się wykonywała do czasu aż warunek ze środka (i < x) nie zostanie spełniony.

//Blok i++ służy do tego aby przy każdej iteracji zwiększać liczbę o 1, natomiast jeżeli będziemy chcieli mieć jakieś inne przypadki możemy również np. dodać 2 co iterację (i+=2) albo inne w zależności od tego co potrzebujemy.

//Dla każdej iteracji możemy odwołać się do zmiennej i (która będzie zawierała w tym przypadku numer iteracji startując od 0)

//Oprócz takiej pętli for możemy wyróżnić również pętle by wykonywać ją przez każdy przypadek np.

for(User u : userList) {
    //code
}

// Gdzie każda iteracja będzie zawierała zmienną u (unikalną) dla swojej iteracji aż przeleci przez wszystkie możliwe obiekty które znajdywałyby się w liście userList
```

---

W javie jeżeli nie chcemy używać za każdym razem bloku `for`, bądź w przypadku kiedy jego zapis nam się nie podoba istnieje również alternatywa, która dla jednej jest ładniejsza w zapisie dla innych nie. W każdym przypadku pokażę wam poniżej abyście mieli również punkt odniesienia gdybyście postanowili kiedyś jej użyć.

```java

List<String> losowaLista = new ArrayList<>();

losowaLista.forEach(user -> {
    //code
});

// W tym przypadku user jest zmienną do której przypisany będzie każdy obiekt podczas iteracji, oraz występuje -> (tzw. lambda expression), który omówimy innym razem. 
```

---

**Listy**

Jak wiecie w Javie aby przechowywać wartości, możemy użyć listy.
jej zapis będziemy zapisywać w sposób

```java
List<T> lista = new Typlisty<>();


/*
Jako, że klasa List jest najbardziej podstawową klasą (interface), od którego są budowane implementacje list 

(tzn. klasy rozszerzają domyślną klasę List).

Tak później używamy docelowego dla nas typu listy którego chcemy użyć.

Z tego co powinniście zapamiętać to fakt, że :

-> ArrayList jest listą która jest najczęściej spotykana z racji na to, że bardzo szybko się przez nią iteruje oraz, że ma bardzo szybki dostęp do danych, oraz że nie jest ona domyślnie sortowana a wartości wkładane do niej będą miały przypisany index
(zaczynający się od 0)

-> LinkedList to lista, rzadko spotykana z racji, że działa na zasadzie, że każdy wkładany bądź wyciągany element prowadzi do następnego tworząc swojego rodzaju ciąg.

Element -> Element -> Element.

oraz posiada funkcję peek() oraz pop() aby odpowiednio wyciągać dane z góry bądź dołu listy.

*/
```

---

**Mapy**

Czasami wartości które będziemy składować chcielibyśmy móc w prosty sposób odszukać. Jednym ze sposobów jak coś takiego zrobić jest aby użyć mapy.

Mapy działają w sposób, że przy wkładaniu podajemy klucz oraz rzecz którą chcemy przechować.

**`Map<K, V>`** gdzie odpowiednio K odpowiada za klucz (Key) a V za value (wartość), którą chcemy przechować.

Tak jak i w przypadku List, Mapy mają kilka implementacji.
Dwie które warto zapamiętać to:

-> **HashMap** który wykorzystywany jest najczęściej z racji, że nie pozwala wrzucać duplikatów (stąd przedrostek Hash który oznacza, że przechowywany jest hashCode rzeczy i po tym jest to sprawdzane)

-> **TreeMap** - Mapa która jest sortowana po kluczu.

---

**Pętla while**

Jeżeli jesteście kreatywni pewnie zadaliście sobie to pytanie przy pętlach for, natomiast dla tych co nie pomyśleli o tym jak wykonywać coś w nieskończoność to przychodzę z odpowiedzią.

Pętla **while** pozwala wykonywać nam coś w nieskończoność do czasu aż warunek przestanie się zgadzać.

```java
while(true) {
    //code
}
```
przykładowo taki while-loop wykonywałby się w nieskończoność z racji, że jego warunek to jest po prostu `true`.

---

**Maven/Gradle oraz inne.**

Te opisane powyżej to menadżery bibliotek z której nasz program korzysta. Dzięki nim możemy w prosty sposób pobierać biblioteki które wymagane są do naszego projektu, a także umożliwiają na wiele różnych rzeczy takich jak buildowanie projektu czy dodawanie akcji post-instalacyjnych.

Ja omówię to całkiem powierzchownie ale dla zainteresowanych głębiej odsyłam do:

[Maven Apache Guide](https://maven.apache.org/guides/getting-started/maven-in-five-minutes.html)

[YouTube Eng](https://www.youtube.com/watch?v=x8sMN4tossY)

[YouTube PL](https://www.youtube.com/watch?v=cYg3zwfdarI)

Najważniejsze jednak co musimy pamiętać, to o strukturze tych technologii z racji, że błędne tagi po prostu spowodują, że nie będą one poprawnie funkcjonować.

Domyślnie wiele z bibliotek które będziemy chcieli korzystać znajdować się będzie na [Maven Central](https://mvnrepository.com), z którego nasz maven domyślnie będzie szukał.

W przypadku gdybyśmy chcieli korzystać z bibliotek które nie znajdują się na głównym maven centralu, możemy dodać własne repozytoria w sekcji

```xml
<repositories>
    <repository>
    ...
    </repository>
</repositories>
```

Gdzie zakomunikujemy jasno, że oczekujemy również bibliotek z naszego źródła.

Wszystkie biblioteki których będziemy chcieli używać będą zapisane w sekcji `<dependencies>`

---

