# Příklady na procvičení

## 1 - Přijímačky ○○○♦♦

Vrať se k příkladu vysvědčení studenta.

```python
school_report = [
    ['Český jazyk', 1],
    ['Anglický jazyk', 1],
    ['Matematika', 1],
    ['Přírodopis', 2],
    ['Dějepis', 1],
    ['Fyzika', 2],
    ['Hudební výchova', 4],
    ['Výtvarná výchova', 2],
    ['Tělesná výchova', 3],
    ['Chemie', 4],
]
```

Při přihlašování na střední školu mohou být důležitější příklady z některých konkrétních předmětů. Uprav kód z lekce
tak, aby spočítal průměr pouze z jazyků, matematiky a fyziky.

### Řešení

```python

sledovane_predmety = [
    'Český jazyk',
    'Anglický jazyk',
    'Matematika',
    'Fyzika',
]

soucet = 0
for predmet_znamka in school_report:
    # rozdelime si dvojici na dve samostatne promenne pro lepsi praci
    predmet = predmet_znamka[0]
    znamka = predmet_znamka[1]
    if predmet in sledovane_predmety:
        soucet += znamka

print(f'Průměr sledovaných předmětů je: {soucet / len(sledovane_predmety)}')
```

## 2 - Rodná čísla ○○♦♦♦

V následujícím seznamu máš seznam rodných čísel pacientů, kteří navštívili v jeden konkrétní den lékařskou ordinaci.

```python
rodna_cisla = [
    '845128/6219',
    '801002/5021',
    '900116/8291',
    '790501/7894',
    '850706/9259',
    '891222/1824',
    '870327/9582',
    '810602/6883',
    '850512/5070',
    '790531/7081'
]
```

- Kolik přišlo mužů a kolik žen?
- Kdy se narodil nejstarší a kdy nejmladší pacient?

*Poznámka:
Pokud nevíš, jak funguje rodné číslo, vysvětlení je níže:
Rodné číslo je identifikační číslo, které slouží k jednoznačné identifikaci osoby. V České republice se rodné číslo
skládá z 10 číslic a jednoho lomítka, které ho rozděluje na části.
Prvních 6 číslic udává datum narození v pořadí rok (2 číslice), měsíc (2 číslice) a den (2 číslice). Například pro
narození 2. února 1990 by prvních 6 číslic mělo být 900202. Zbytek rodného čísla (tj. část za lomítkem) slouží k
identifikaci konkrétní osoby.
Ženy mají k číslu měsíce přičteno 50, např. 845128/6219 je číslo patřící ženě.*

### Řešení

```python
pocet_muzu = 0
nejmladsi_rok = 0
nejstarsi_rok = 1000  # na začátek nastavíme na vysokou hodnotu

for rodne_cislo in rodna_cisla:
    rok = int(rodne_cislo[:2])

    # porovname s nejstarsim
    if rok < nejstarsi_rok:
        nejstarsi_rok = rok

    # porovname s nejmladsim
    if rok > nejmladsi_rok:
        nejmladsi_rok = rok

    # zjistime pohlavi
    mesic = int(rodne_cislo[2:4])
    if mesic < 50:
        pocet_muzu += 1

print(f'nejmladší se narodil v roce {nejmladsi_rok}')
print(f'nejstarší se narodil v roce {nejstarsi_rok}')
print(f'přišlo {pocet_muzu} mužů')
```

## 3 - Fahrenheit vs. Celsius ○○○♦♦

Pokud pečete podle anglických receptů, často se po váš požaduje rozehřát troubu na uvedenou teplotu. Pokud si ovšem
neuvědomíte, že Američané používají pro měření teploty stupně Fahrenheita namísto Celsia, bude vás na konci pečení čekat
nemilé překvapení.

Nastudujte si na České Wikipedii jak se převádějí stupně Fahrenheita na stupně Celsia a napište program, který takový
převod provede. Váš program se zeptá uživatele na teplotu ve stupních Fahrenheita a vypíše její ekvivalent ve stupních
Celsia.

### Řešení

```python
fahrenheit = float(input('Zadej teplotu ve stupních Fahrenheita: '))

celsius = (5 * (fahrenheit - 32)) / 9

print(f'Teplota ve stupních Celsia je: {round(celsius, 2)}')
```