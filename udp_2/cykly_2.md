# Cvičení: Další příklady cyklů

## 1 - Tombola ○○○♦♦

V tombole bylo prodáno celkem 1000 lístků. Naším úkolem je vylosovat náhodně tři výherce. Napište program, který
vygeneruje a vypíše tři čísla mezi 1 a 1000.  
Využijte funkci `randint`, nezapomeňte ale, že si ji musíte importovat z modulu `random`.

Neřešte, že jedno číslo může být vygenerováno dvakrát.

### Řešení

```python
import random

for _ in range(3):
    print(random.randint(1, 1000))
```

## 2 - Dělitelnost více čísly ○○○♦♦

Vypišme si čísla z nějakého rozsahu na základě jejich dělitelnosti dvěma čísly.

- Zkuste z nějakého rozsahu čísel vypsat čísla, která jsou dělitelná 3 i 4 současně.
- Zkuste z nějakého rozsahu čísel vypsat čísla, která jsou dělitelná 5 nebo 6.  
  Stačí vypsat text: `"Číslo je dělitelné 5 nebo 6."`

### Řešení

```python
for n in range(30):
    delitelne_3 = n % 3 == 0
    delitelne_4 = n % 4 == 0
    if delitelne_3 and delitelne_4:
        print(f'{n} je dělitelné 3 i 4')

    delitelne_5 = n % 5 == 0
    delitelne_6 = n % 6 == 0
    if delitelne_5 or delitelne_6:
        print(f'{n} je dělitelné 5 nebo 6')
```

## 3 - Seznam hostů na párty ○○○♦♦

Vraťte se k příkladu se zadáváním seznamu hostu na párty a zkopírujte si kód k sobě do editoru.  
Upravte program tak, že pokud uživatel v průběhu zadávání jmen napíše "konec", cyklus na zadávání jmen se ukončí.

### Řešení

```python
number_of_guests = int(input("Zadej počet hostů: "))
guest_list = []
for i in range(number_of_guests):
    new_guest = input("Zadej jméno hosta: ")
    if new_guest == 'konec':
        break
    guest_list.append(new_guest)
print(guest_list)
```

# Bonusy

## 4 - Prvočíslo ○♦♦♦♦

Požádej uživatele o zadání celého čísla. Následně urči, zda je toto číslo prvočíslo.

Prvočíslo je číslo, které je dělitelné beze zbytku pouze 2 čísly - 1 a sebou samotným.

- Například 5 je prvočíslo, protože je dělitelná pouze 1 a 5.
- Naopak 4 není prvočíslo, protože je dělitelná 1, 2 a 4.

### Řešení

*pozn.: Níže je velmi neefektivní způsob. Samozřejmě existují specializované algorytmy.*

```python
testovane = int(input('Zadej číslo na otestování: '))

prvocislo = True
for n in range(2, testovane):
    if testovane % n == 0:
        prvocislo = False
        break

print(f'cislo {testovane} {"je" if prvocislo else "není"} prvocislo')
```

---

# Cvičení: Cyklus while

## 1 - Hádání čísla ○♦♦♦♦

Napište interaktivní hru, ve které počítač vygeneruje tajné číslo v rozsahu 1 až 100 (použijte
funkci `random.randint()`).  
Následně se v cyklu ptejte uživatele, aby zadal číslo a vypisujte vždy jestli je zadané číslo nižší nebo vyšší než tajné
číslo. Ukončete cyklus v momentě, kdy uživatel trefí tajné číslo.

### Řešení

```python
import random

hadane_cislo = random.randint(1, 100)

while True:
    tip = int(input('hádej: '))

    if tip == hadane_cislo:
        print('Uhodl jsi!')
        break

    if tip > hadane_cislo:
        print('hadane cislo je nižší')
    elif tip < hadane_cislo:
        print('hádané číslo je vyšší')
```

---

# Cvičení: list comprehension

## 1 - Seznamy čísel ○○○○♦

Mějme zadaný následující seznam

```python
cisla = [1.12, 4.51, 2.64, 13.1, 0.1]
```

Vytvořte seznam, který obsahuje

- každé z čísel ze seznamu cisla vynásobené dvěma,
- každé z čísel ze seznamu cisla s opačným znaménkem,
- každé z čísel ze seznamu cisla umocněné na druhou,
- každé z čísel ze seznamu cisla jako řetězec.

### Řešení

```python
krat_dva = [n * 2 for n in cisla]
minus = [-n for n in cisla]
na_druhou = [n ** 2 for n in cisla]
jako_str = [str(n) for n in cisla]
```

## 2 - Seznamy řetězců ○○○♦♦

Mějme zadaný následující seznam

```python
jmena = ['Roman', 'Jan', 'Miroslav', 'Petr', 'Gabriel']
```

Vytvořte seznam, který obsahuje

- počty písmen ve všech jménech,
- všechna jména napsaná velkými písmeny,
- všechna jména plus písmeno 'a' na konci (stanou se z nich tedy ženská jména),
- všechna jména převedená na malá písmena s koncovkou '@email.cz'.

### Řešení

```python
pocty = [len(jmeno) for jmeno in jmena]
velkymi = [jmeno.upper() for jmeno in jmena]
s_ackem = [jmeno + 'a' for jmeno in jmena]
emaily = [f'{jmeno.lower()}@email.cz' for jmeno in jmena]
```

## 3 - Seznam teplot ○○♦♦♦

Mějme zadaný následující seznam naměřených teplot. Seznam obsahuje teploty naměřené pro každý den v týdnu ve čtyřech
časech - ráno, v poledne, večer a v noci.

```python
teploty = [
    [2.1, 5.2, 6.1, -0.1],
    [2.2, 4.8, 5.6, -1.0],
    [3.3, 6.5, 5.9, 1.2],
    [2.9, 5.6, 6.0, 0.0],
    [2.0, 4.6, 5.5, -1.2],
    [1.0, 3.2, 2.1, -2.0],
    [0.4, 2.7, 1.3, -2.8]
]
```

- Vytvořte seznam průměrných teplot pro každý den.
- Vytvořte seznam ranních teplot.
- Vytvořte seznam nočních teplot.
- Vytvořte seznam dvouprvkových seznamů obsahujících pouze polední a noční teplotu.

### Řešení

```python
import statistics

prumery = [statistics.mean(den) for den in teploty]
ranni = [den[0] for den in teploty]
nocni = [den[-1] for den in teploty]
poledne_a_noc = [[den[1], den[-1]] for den in teploty]
```

## 4 - Čtení kódu ○○○♦♦

V této úloze jde o pochopení kódu.  
Nemá tak dané řešení.

---

# Doporučené úložky na doma

## 5 - Ověřování věku ○○○○♦

Následující seznam obsahuje věky uživatelů naší malé sociální sítě.

```python
veky = [35, 12, 44, 11, 18, 21, 28, 18]
```

- Vytvořte pomocí chroustání seznamů seznam celých čísel, které udávají, kolik jednotlivým uživatelům zbývá do 18ti let.
  Záporná čísla budou znamenat, že uživatel už věk překročil.
- Vytvořte pomocí chroustání seznamů seznam pravdivostních hodnot, které udávají, který uživatel je starší 18ti let.
- Vytvořte pomocí chroustání seznamů seznam pravdivostních hodnot, které udávají, který uživatel má přesně 18 let.

### Řešení

```python
zbyva_do_18 = [18 - vek for vek in veky]
starsi_18 = [vek > 18 for vek in veky]
stary_presne_18 = [vek == 18 for vek in veky]
```

## 6 - Promítání ○○○♦♦

V letním kině Šmajchl mají program na každý den uložený jako dva seznamy. První seznam obsahuje názvy filmů a druhý
jejich délky v minutách, např. takto:

```python
nazvy = [
    'Někdo to rád horké, extended edition',
    'Adéla ještě nevečeřela',
    'Kulový blesk'
]
delky = [136, 105, 82]
```

Použijte chroustání seznamů a vyrobte seznam trvání, který bude obsahovat délky filmů nikoliv jako čísla v minutách, ale
jako řetězce v hodinách a v minutách. Výsledek tedy bude vypadat takto

```python
trvani = ['2:16', '1:45', '1:22']
```

### Řešení

```python
trvani = [f'{d // 60}:{d % 60}' for d in delky]
```

## 7 - Počty obyvatel ○○○♦♦

Mějme počty obyvatel v jednotlivých krajích ČR podle následující tabulky.

| Kraj                 | Počet obyvatel |
|----------------------|----------------|
| Hlavní město Praha   | 1 280 508      |
| Jihočeský kraj       | 638 782        |
| Jihomoravský kraj    | 1 178 812      |
| Karlovarský kraj     | 296 749        |
| Kraj Vysočina        | 508 952        |
| Královéhradecký kraj | 550 804        |
| Liberecký kraj       | 440 636        |
| Moravskoslezský kraj | 1 209 879      |
| Olomoucký kraj       | 633 925        |
| Pardubický kraj      | 517 087        |
| Plzeňský kraj        | 578 629        |
| Středočeský kraj     | 1 338 982      |
| Ústecký kraj         | 821 377        |
| Zlínský kraj         | 583 698        |

Tuto tabulku máme reprezentovanou jako seznam:

```python
kraje = [
    ['Hlavní město Praha', '1 280 508'],
    ['Jihočeský kraj', '638 782'],
    ['Jihomoravský kraj', '1 178 812'],
    ['Karlovarský kraj', '296 749'],
    ['Kraj Vysočina', '508 952'],
    ['Královéhradecký kraj', '550 804'],
    ['Liberecký kraj', '440 636'],
    ['Moravskoslezský kraj', '1 209 879'],
    ['Olomoucký kraj', '633 925'],
    ['Pardubický kraj', '517 087'],
    ['Plzeňský kraj', '578 629'],
    ['Středočeský kraj', '1 338 982'],
    ['Ústecký kraj', '821 377'],
    ['Zlínský kraj', '583 698']
]
```

- Vytvořte seznam, který obsahuje pouze názvy všech krajů, tedy první sloupeček této tabulky.
- Vytvořte seznam, který obsahuje počty obyvatel jako čísla. Pro zbavení se mezer v číslech se vám jistě bude hodit
  metoda řetězců jménem replace().
- Do vhodně pojmenované proměnné uložte seznam, který reprezentuje výše uvedenou tabulku jako dva seznamy: seznam jmen a
  seznam počtů obyvatel jako čísla.

### Řešení

```python
nazvy = [kraj[0] for kraj in kraje]
obyvatele = [int(kraj[-1].replace(' ', '')) for kraj in kraje]

jmena_a_pocty = [
  [kraj[0] for kraj in kraje],
  [int(kraj[-1].replace(' ', '')) for kraj in kraje],
]
```

## 8 - Volby ○○♦♦♦

Máme pět kandidátů na post prezidenta ČR. Následující tabulka obsahuje hlasy, které jednotliví kandidáti získali v prvním kole prezidentských voleb.

| Kraj                 | Igor Rezek | Augustýn Doležal | Vladan Bednář | Ondřej Brotz | Radim Kašpar |
|----------------------|------------|------------------|---------------|--------------|--------------|
| Hlavní město Praha   | 78774      | 43179            | 225111        | 144799       | 242854       |
| Jihočeský kraj       | 91062      | 22451            | 17475         | 53391        | 46450        |
| Jihomoravský kraj    | 179186     | 216499           | 4493          | 156305       | 61222        |
| Karlovarský kraj     | 9619       | 53476            | 926           | 64737        | 34566        |
| Kraj Vysočina        | 66904      | 85730            | 27271         | 12964        | 38041        |
| Královéhradecký kraj | 118755     | 1929             | 30426         | 25178        | 31952        |
| Liberecký kraj       | 64467      | 40993            | 81181         | 39392        | 4335         |
| Moravskoslezský kraj | 11221      | 97970            | 26179         | 98539        | 112578       |
| Olomoucký kraj       | 171064     | 7638             | 8752          | 96666        | 39738        |
| Pardubický kraj      | 74235      | 101680           | 18920         | 45904        | 1922         |
| Plzeňský kraj        | 39309      | 1505             | 10531         | 30458        | 40228        |
| Středočeský kraj     | 131584     | 1812             | 241122        | 22267        | 99326        |
| Ústecký kraj         | 194133     | 39985            | 200997        | 28229        | 20780        |
| Zlínský kraj         | 66188      | 51607            | 15977         | 177272       | 17664        |

Data máme k dispozici v následujícím formátu

```python
hlasy = [
    [78774, 43179, 225111, 144799, 242854],
    [91062, 22451, 17475, 53391, 46450],
    [179186, 216499, 4493, 156305, 61222],
    [9619, 53476, 926, 64737, 34566],
    [66904, 85730, 27271, 12964, 38041],
    [118755, 1929, 30426, 25178, 31952],
    [64467, 40993, 81181, 39392, 4335],
    [11221, 97970, 26179, 98539, 112578],
    [171064, 7638, 8752, 96666, 39738],
    [74235, 101680, 18920, 45904, 1922],
    [39309, 1505, 10531, 30458, 40228],
    [131584, 1812, 241122, 22267, 99326],
    [194133, 39985, 200997, 28229, 20780],
    [66188, 51607, 15977, 177272, 17664]
]
```

Zodpovězte následující otázky:

- Kolik získal každý kandidát hlasů v celé ČR?
- Který kandidát vyhrál první kolo voleb?
- Ve kterých krajích byla nejvyšší a nejnižší volební účast
- Vytvořte tabulku, která ukazuje který kandidát vyhrál v kterém kraji.
- Vytvořte tabulku podobnou té z tohoto cvičení, která místo čísel bude obsahovat jaké procento celkového počtu hlasů získal každý kandidát v daném kraji.

**Nápověda**: postupuje tak, že použijete na každý řádek tabulky zvlášť chroustání seznamů. Tabulku můžete sestavit tak, že tento postup ručně zopakujete 13 krát, jednou pro každý kraj. Pokud toužíte po elegantnějším řešení, vyčkejte na nepovinné úložky.

### Řešení

```python
# soucty hlasu po kandidatech
soucty_hlasu = []
for poradi_kandidata in range(len(hlasy[0])):
    soucet_za_kandidata = 0
    for kraj in hlasy:
        soucet_za_kandidata += kraj[poradi_kandidata]
    soucty_hlasu.append(soucet_za_kandidata)
print(soucty_hlasu)

# ktery vyhral
cislo_viteze = soucty_hlasu.index(min(soucty_hlasu))
print(cislo_viteze)

# nejvyssi a nejnizsi ucast
ucasti = [sum(kraj) for kraj in hlasy]
nejnizsi = ucasti.index(min(ucasti))
nejvyssi = ucasti.index(max(ucasti))
print(f'kraj s nejinzsi ucasti je {nejnizsi}')
print(f'kraj s nejvyssi ucasti je {nejvyssi}')

# procenta celkoveho poctu
procenta = []
for kraj in hlasy:
    soucet = sum(kraj)
    procenta.append(
        [round((kandidat / soucet) * 100, 2) for kandidat in kraj]
    )
print(procenta)
```

---

# Volitelné úložky na doma

## 9 - Elegantní volby ○♦♦♦♦

Pokud vás trápí, že řešení varianty e) v úloze o volbách není příliš elegantní, zkuste sestavit Python výraz na jeden řádek, 
který celý bod e) vyřeší najednou. Bude potřeba do sebe zanořit dvě chroustání seznamů, jedno přes hodnoty v řádcích a druhé přes jednotlivé kraje.

### Řešení

```python
# procenta celkoveho poctu
procenta = [
    [round((kandidat / sum(kraj)) * 100, 2) for kandidat in kraj]
    for kraj in hlasy
]
print(procenta)
```


