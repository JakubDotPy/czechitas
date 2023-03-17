# Cvičení: Seznamy

## 1 - Pohyby na účtu ○○○♦♦

Mějme seznam pohybů na nějakém bankovním účtu:

```python
pohyby = [1200, -250, -800, 540, 721, -613, -222]
```

- Vypište v pořadí třetí pohyb z uvedeného seznamu.
- Vypište všechny pohyby kromě prvních dvou.
- Vypište kolik je všech pohybů dohromady.
- Pomocí volání vhodných funkcí vypište nejvyšší a nejnižší pohyb.
- Spočítejte celkový přírůstek na účtu za dané období. Pozor, že přírůstek může vyjít i záporný.

### Řešení

```python
pohyby = [1200, -250, -800, 540, 721, -613, -222]

# v poradi treti
print(pohyby[2])

# vsechny krome dvou prvnich
print(pohyby[2:])

# vsechny dohromady
print(len(pohyby))

# nejvyssi a nejnizsi
print(f'nejnizsi je {min(pohyby)}, nejvyssi {max(pohyby)}')

# celkovy prirustek
print(f'zustatek = {sum(pohyby)}')
```

## 2 - Průměr ○○○♦♦

Mějme proměnnou `s`, ve které předpokládáme uložený nějaký seznam.  
Sestavte v výraz (vzoreček), který spočítá průměrnou hodnotu v takovém seznamu. Otestujte jej na seznamech různých
délek.

### Řešení

```python
s = [1, 2, 3, 5, 8, 15, 56]
prumer = sum(s) / len(s)
print(f'prumer {s} je {prumer}')
```

## 3 - Rozpětí ○○○♦♦

Postupujte obdobně jako v úložce Průměr, ale tentokrát sestavte výraz pro výpočet rozpětí, tedy rozdílu mezi minimální a
maximální hodnotou.

### Řešení

```python
s = [1, 2, 3, 5, 8, 15, 56]
rozpeti = max(s) - min(s)
print(f'rozpeti {s} je {rozpeti}')
```

# Bonusy

## 4 - Střed seznamu ○♦♦♦♦

Sestavte výraz, který vrátí číslo nacházející se přesně uprostřed v zadaném seznamu `s`.
U seznamů liché délky je střed jasně definovaný, ovšem u seznamů sudé délky nám padne mezi dvě čísla. V takovém případě
vyberte jako střed číslo blíže ke konci seznamu.

### Řešení

```python
s = [1, 2, 3, 5, 8, 15, 56]

stred = s[len(s) // 2]

print(f'stred {s} je {stred}')
```

## 5 - Střed seznamu podruhé ♦♦♦♦♦♦

Sestavte vzoreček, který vrátí číslo nacházející se přesně uprostřed v zadaném seznamu s.
Tentokrát však u seznamů sudé délky vyberte jako střed číslo blíž k začátku seznamu.

### Řešení

```python
s = [1, 2, 3, 5, 8, 15, 56]

if len(s) % 2 == 0:  # je sudy
    index = len(s) // 2 - 1
else:
    index = len(s) // 2

stred = s[index]

print(f'stred {s} je {stred}')
```

---

# Cvičení: Řetězce, metody

## 1 - Převod písmen ○○○○♦

Uložte si do proměnné `jmeno` svoje jméno.  
Pomocí volání vhodných metod jej převeďte nejdříve na malá písmena a poté na velká písmena.

### Řešení

```python
jmeno = 'Kuba'
print(jmeno.lower())
print(jmeno.upper())
```

## 2 - Čísla jako text ○○○♦♦

Mějme seznam čísel zadaných jako text

```python
hodnoty = ['12', '1', '7', '-11']
```

Potřebujeme k třetímu číslu v seznamu přičíst 4, aby výsledek vypadal takto:

```python
hodnoty = ['12', '1', '11', '-11']
```

Před tím, než se podíváte na následující kroky, sami si rozmyslete postup, jak toto provést. Až když si nejste jistí,
pokračujte podle následujících kroků.

- Uložte si hodnotu na třetí pozici v seznamu do nějaké proměnné.
- Převeďte tuto hodnotu na číslo a přičtěte k němu 4. Výsledek uložte do proměnné vysledek.
- Převeďte hodnotu v proměnné vysledek zpět na řetězec a uložte ji na třetí pozici v seznamu hodnoty.

### Řešení

```python
hodnoty = ['12', '1', '7', '-11']

treti = hodnoty[2]
prepocteno = int(treti) + 4
hodnoty[2] = prepocteno
```

## 3 - Čísla v textu ○○♦♦♦

Máme obdobné zadání jako v předchozím cvičení, avšak tentokrát máme čísla zadána nikoliv v seznamu, ale v řetězci
oddělená mezerou:

```python
hodnoty = '12.1 1.68 7.45 -11.51'
```

K poslednímu číslu v seznamu chceme přičíst `0.25` tak, aby výsledek vypadal takto

```python
hodnoty = '12.1 1.68 7.45 -11.26'
```

Určitě se vám budou hodit metody `split` a `join`.

### Řešení

```python
hodnoty = '12.1 1.68 7.45 -11.51'
hodnoty_list = hodnoty.split()

posledni = hodnoty_list[-1]
prepocteno = float(posledni) + 0.25
hodnoty_list[-1] = str(prepocteno)

hodnoty = ' '.join(hodnoty_list)
```

# Bonusy

## 4 - Chytřejší čísla jako text ○♦♦♦♦

Zkuste vymyslet, jak udělat zápis příkazů ze cvičení `Čísla jako text` co nejúspornější.  
Dá se dojít až k tomu, že celé řešení bude na jeden řádek.

### Řešení

```python
hodnoty = ['12', '1', '7', '-11']
hodnoty[2] = str(int(hodnoty[2]) + 4)
print(hodnoty)
```

---

# Cvičení: Moduly

## 1 - Zaokrouhlování ○○○○♦

Napište program, který dostane na vstupu desetinné číslo a na výstup napíše toto číslo zaokrouhlené nejdříve nahoru,
potom dolů a potom běžným Pythonovským zaokrouhlováním.

### Řešení

```python
import math

num = float(input('zadej cislo: '))

print(f'nahoru: {math.ceil(num)}')
print(f'dolu:  {math.floor(num)}')
print(f'round: {round(num)}')
```

## 2 - Přijímačky a moduly ○○○♦♦

Uvažujme vysvědčení studenta, které máme uložené jako seznam.

```python
school_report = [
    ["Český jazyk", 1],
    ["Anglický jazyk", 1],
    ["Matematika", 1],
    ["Přírodopis", 2],
    ["Dějepis", 1],
    ["Fyzika", 2],
    ["Hudební výchova", 4],
    ["Výtvarná výchova", 2],
    ["Tělesná výchova", 3],
    ["Chemie", 4],
]
```

Uvažuj, že student se hlásí na školu, která vybírá studenty podle průměru.  
Pro školu jsou ale důležité pouze předměty český jazyk, anglický jazyk, matematika a fyzika. Vypočítej průměr studenta z
daných předmětů s využitím modulu `statstics`.  
Na začátku vytvoř prázdný seznam a následně pomocí cyklu vlož do nového seznamu známky ze čtyř vyjmenovaných předmětů.
Nakonec použij metodu `statistics.mean()` k výpočtu průměru.
Dále zkus využít funkce, které jsou zmíněné v textu, k výpočtu nejlepší a nejhorší známky z daných předmětů.

### Řešení

```python
import statistics

sledovane_predmety = [
    'Český jazyk',
    'Anglický jazyk',
    'Matematika',
    'Fyzika',
]

sledovane_znamky = []

for predmet_znamka in school_report:
    # rozdelime si dvojici na dve samostatne promenne pro lepsi praci
    predmet = predmet_znamka[0]
    znamka = predmet_znamka[1]
    if predmet in sledovane_predmety:
        sledovane_znamky.append(znamka)

print(f'průměr sledovaných předmětů je {statistics.mean(sledovane_znamky)}')
print(f'nejlepší je {min(sledovane_znamky)}')
print(f'nejhorší je {max(sledovane_znamky)}')
```

## 3 - Přijímačky a moduly ○○○♦♦

Ve statistice existuje ukazatel zvaný _modus_, který vrátí nejčastější hodnotu v datech. V modulu `statistics` existuje
funkce `mode()`, která umí modus spočítat. Funkce `mode()` má navíc vychytávku, umí pracovat i s řetězci.

Uvažuj data v seznamu `votes`, což je hlasování zaměstnanců malé firmy o tom, jakou akci podniknou během jejich
vánočního večírku. Použij funkce `mode()` ke zjištění, pro jakou aktivitu hlasovalo nejvíce zaměstnanců. Funkce má jeden
parametr - seznam, ze kterého má určit nejčastější prvek.

### Řešení

```python
import statistics

votes = [
    "curling",
    "vánoční svařák na trzích",
    "vánoční svařák na trzích",
    "curling",
    "zážitková první pomoc",
    "curling",
    "zážitková první pomoc",
    "curling",
    "zážitková první pomoc",
]

print(f'nejčastější volbou bylo: {statistics.mode(votes)}')
```

---

# Další příklady na procvičení

## 1 - Průměrné teploty ○○○♦♦

Následující tabulka obsahuje průměrné roční teploty v České republice za roky 2001 až 2010 (zdroj: Český
hydrometeorologický ústav).

| rok  | teplota °C |
|------|------------|
| 2001 | 	7.8       |
| 2002 | 	8.7       |
| 2003 | 	8.2       |
| 2004 | 	7.8       |
| 2005 | 	7.7       |
| 2006 | 	8.2       |
| 2007 | 	9.1       |
| 2008 | 	8.9       |
| 2009 | 	8.4       |
| 2010 | 	7.2       |

Vytvořte reprezentaci této tabulky pomocí seznamu seznamů. Zde existují dvě možnosti.  
Nejprve vytvořte seznam, který obsahuje řádky tabulky jako dvouprvkové seznamy a uložte jej do proměnné `radky`.  
Poté vytvořte seznam, který obsahuje sloupce tabulky, tedy dva seznamy po deseti prvcích. Uložte jej do
proměnné `sloupce`.

Pro obě tyto reprezentace vyřešte následující úkoly

- Získejte teplotu na třetím řádku tabulky.
- Získejte rok na pátém řádku tabulky.
- Získejte poslední řádek tabulky jako seznam.
- Vytvořte tabulku bez prvních dvou řádků.
- Vytvořte tabulku pouze z prvních dvou řádků.
- Vytvořte tabulku obsahující jen řádky 5, 6, 7, 8 (myšleno při "lidském" číslování, tj. od 1).
- Použitím proměnné `sloupce` vypište seznam teplot seřazený vzestupně podle velikosti. Šlo by to i pomocí
  proměnné `radky`, ale to ještě neumíme.

### Řešení

```python
radky = [
    [2001, 7.8],
    [2002, 8.7],
    [2003, 8.2],
    [2004, 7.8],
    [2005, 7.7],
    [2006, 8.2],
    [2007, 9.1],
    [2008, 8.9],
    [2009, 8.4],
    [2010, 7.2],
]

# Získejte teplotu na třetím řádku tabulky.
radky[2][1]

# Získejte rok na pátém řádku tabulky.
radky[4][0]

# Získejte poslední řádek tabulky jako seznam.
radky[-1]

# Vytvořte tabulku bez prvních dvou řádků.
radky[2:]

# Vytvořte tabulku pouze z prvních dvou řádků.
radky[:2]

# Vytvořte tabulku obsahující jen řádky 5, 6, 7, 8 (myšleno při "lidském" číslování, tj. od 1).
radky[4:8]

sloupce = [
    [2001, 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010],
    [7.8, 8.7, 8.2, 7.8, 7.7, 8.2, 9.1, 8.9, 8.4, 7.2],
]

# Použitím proměnné sloupce vypište seznam teplot seřazený vzestupně podle velikosti.
print(sorted(sloupce[1]))
```

## 2 - Známky z písemek ○○♦♦♦

Máme data o písemce, která obsahovala 4 otázky. Za každou otázku mohl student (studentka) získat max. 10 bodů.  
Výsledky studentů jsou v následující tabulce.

| Student | Otázka 1 | Otázka 2 | Otázka 3 | Otázka 4 |
|---------|----------|----------|----------|----------|
| A       | 9        | 7        | 8        | 5        |
| B       | 5        | 3        | 6        | 6        |
| C       | 8        | 4        | 9        | 7        |
| D       | 8        | 5        | 4        | 8        |
| E       | 10       | 6        | 10       | 7        |

Ulož si známky studentů do dvourozměrného seznamu.

Spočítej známku jednotlivých studentů. Známku urči podle celkového počtu bodů ze všech příkladů. Bodovací tabulku najdeš
níže.

| Body        | Známka |
|-------------|--------|
| 36 a více   | 1      |
| 32 a více   | 2      |
| 26 a více   | 3      |
| 20 a více   | 4      |
| méně než 20 | 5      |

Vypočítej průměrné body z jednotlivých otázek. Ze které otázky dostali studenti v průměru nejvíce bodů? A ze které
naopak nejméně?

### Řešení

```python
tabulka_bodu = [
    ['A', 9, 7, 8, 5],
    ['B', 5, 3, 6, 6],
    ['C', 8, 4, 9, 7],
    ['D', 8, 5, 4, 8],
    ['E', 10, 6, 10, 7],
]

body_celkem = []
for student_znamky in tabulka_bodu:
    # rozdlel na studenta a body
    student = student_znamky[0]
    body = student_znamky[1:]

    celkem_bodu = sum(body)

    # urci znamku
    if celkem_bodu < 20:
        znamka = 5
    elif celkem_bodu <= 26:
        znamka = 4
    elif celkem_bodu <= 32:
        znamka = 3
    elif celkem_bodu <= 36:
        znamka = 2
    else:
        znamka = 1

    # vypis
    print(f'student {student} dostal {znamka}')

# Vypočítej průměrné body z jednotlivých otázek.
# Ze které otázky dostali studenti v průměru nejvíce bodů? A ze které naopak nejméně?

# přepíšeme si tabulku
tabulka_po_sloupcich = [
    ['A', 'B', 'C', 'D', 'E'],
    [9, 5, 8, 8, 10],
    [7, 3, 4, 5, 6],
    [8, 6, 9, 4, 10],
    [5, 6, 7, 8, 7],
]

import statistics

prumery = []
for radek in tabulka_po_sloupcich[1:]:
    prumery.append(statistics.mean(radek))

print(prumery)

# z výsledného seznamu je možné vyčíst jednotlivé průměry
```

## 3 - Zasedačka ○○♦♦♦

Níže máš seznam akcí, které se konaly v zasedačce jedné firmy.

```python
akce = [
    "školení - řízení firemních vozidel",
    "jazykový kurz - angličtina",
    "pohovor - Jan Dvořák",
    "pohovor - Antonín Sova",
    "jazykový kurz - němčina",
    "pohovor - Iveta Hájková",
    "pohovor - Ivan Brož",
    "pohovor - Katarína Martináková",
    "setkání se zákazníkem - Metrostav",
    "jazykový kurz - angličtina",
    "školení - vykazování práce",
    "pohovor - Klaudie Moudrusová",
]
```

Napiš program, který zjistí následující:

- Kolik se uskutečnilo pohovorů?
- V jakých jazycích se mohou zaměstnanci firmy vzdělávat?

Při řešení můžeš využít operátor `in` a slicing, případně metodu `split()`

### Řešení

```python
dostupne_jazyky = []
pocet_pohovoru = 0

for radek_text in akce:

    # rozdelim a ulozim do dvou promennych
    radek = radek_text.split(' - ')
    typ = radek[0]
    data = radek[1]

    if typ == 'jazykový kurz':
        # musime zkontrolovat, jestli uz v seznamu nemame
        if data not in dostupne_jazyky:
            dostupne_jazyky.append(data)

    if typ == 'pohovor':
        pocet_pohovoru += 1

print(f'dostupne jazyky jsou {dostupne_jazyky}')
print(f'bylo {pocet_pohovoru} pohovoru')
```
