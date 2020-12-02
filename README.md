# C# Basis

## a. Strings
Is niets anders als tekst, gedefinieerd als volgt:

```C#
string tekst = "Hallo wereld";
```

## b. Strings samenvoegen
Als je twee of meer strings wilt samenvoegen doe je dat d.m.v. concateneren:

```C#
string hallo = "Hallo";
string wereld = "wereld";

string halloWereld = hallo + ", " + wereld;
```

## c. String interpoleren

```C#
string hallo = "Hallo";
string wereld = "wereld";

string halloWereld = $"{hallo}, {wereld}";
```

## d. String functies
```C#
string hallo = "   Hallo   ";
hallo.Length; // Telt alle karakters inclusief spaties: 11
hallo.Trim().Length(); // Telt zonder spaties aan uiteinden: 5
hallo.Replace(" ", "").Length; // Telt alle karakters ZONDER spaties: 5
```

Zoek ook eens naar functies als String.Contains(); voor bijv zoektekst en if statements.

## e. Numbers

```C#
int // Altijd een heel getal, bijv. 5
float // (Single) een precies getal met cijfers achter de komma, bijv. 5,112374564
double // Een getal met twee cijfers achter de komma, bijv. 5,11
decimal // Een getal met cijfers achter de komma naar keuze, bijv. 5,1124
```

Rekenen met getallen:

```C#
int a = 7, b = 4, c = 3;

int d = (a + b) / c; // d = 3
int e = (a + b) % c; // e = 2, want 3x3=9 en 11-9 = 2
```

## f. Variabelen

Variabelen zijn gegevens die tijdelijk worden opgeslagen in het geheugen tot ze niet meer gebruikt worden.

Voorbeelden zijn:

```C#
int a = 2;
int b = 3;
string c = "Hallo";
double d = 10.34;
decimal e = 10.348347m;
float f = 10.348927354723894f;

var g = "Test"; // String
var h = 2.33; // Double
```

## g. Classes

Classes zijn een stukje code waarin je meerdere variabele typen kunt plaatsen die gecombineerd gebruikt worden.

```C#
public class Afspraak
{
    public int Id { get; set; }
    
    public string Titel { get; set; }
    public string Notitie { get; set; }
    
    public DateTime Wanneer { get; set; }
}
```

Elders is de applicatie kunnen we deze class nu gebruiken als ons nieuwe type variabele, alleen moeten we een geheugen plek toewijzen voor deze 'grote' variabele.

```C#
Afspraak a = new Afspraak();
a.Id = 1;
a.Titel = "Heui, de eerste afspraak";
a.Notitie = "Deze notitie slaat op de afspraak met ID 1";
a.Wanneer = DateTime.Now;

Afspraak b = new Afspraak();
...
```

of

```C#
var a = new Afspraak
{
    Id = 1,
    Titel = "Heui, de eerste afspraak",
    Notitie = "Deze notitie slaat op de afspraak met ID 1",
    Wanneer = DateTime.Now
};
```

En als we een lijst van onze afspraak klasse willen, maken we gebruik van collections of arrays, lists:

Arrays gebruik je alleen als je van tevoren weet hoeveel items er zijn in de lijst. Een collection gebruik je als je niet weet hoeveel items er zijn in de lijst (stuk dynamischer).

```C#
// ARRAYS
int[] getallen = new int[5] { 1, 2, 3, 4, 5 };
Afspraak[] afspraken = new Afspraak[5] { ... }

// LIST
List<int> getallen = new List<int> { 1, 2, 3, 4, 5 };
List<Afspraak> afspraken = new List<Afspraak> { ... };

getallen.Add(6); // Dit kan alleen met lijsten
```

