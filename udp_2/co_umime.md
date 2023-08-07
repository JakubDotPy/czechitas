# Příklady na procvičení

## 1 - Součet čísel v seznamu ○○○○♦

Napiš kód, který zpracuje seznam čísel a vypíše jejich součet (bez použití funkce `sum()`).

### Řešení

```python
soucet = 0

for cislo in [1, 2, 3, 4]:
    soucet += cislo

print(soucet)
```

## 2 - Největší prvek v seznamu ○○○○♦

Napiš kód, který zpracuje seznam čísel a vypíše největší prvek v tomto seznamu (bez použití funkce `max()`).

### Řešení

```python
nejvetsi = 0

for cislo in [1, 2, 100, 3, 4]:
    if cislo > nejvetsi:
        nejvetsi = cislo

print(nejvetsi)
```

## 3 - Sudá čísla ○○○♦♦

Napiš kód, který zpracuje seznam čísel a vypíše pouze sudá čísla z tohoto seznamu.

### Řešení

```python
for cislo in [1, 2, 100, 3, 4]:
    if cislo % 2 == 0:
        print(cislo)
```

## 4 - Rozdělení čísel ○○○♦♦

Napiš kód, který zpracuje seznam čísel a vytvoří nový seznam se sudými čísly a nový seznam s lichými čísly z původního
seznamu.

### Řešení

```python
sude = []
liche = []

for cislo in [1, 2, 100, 3, 4]:
    if cislo % 2 == 0:
        sude.append(cislo)
    else:
        liche.append(cislo)

print(sude)
print(liche)
```

## 5 - Odstranění duplikátŮ ○○○♦♦

Napiš kód, který zpracuje seznam a vytvoří nový seznam bez duplikátů. Výsledné pořadí prvků musí být zachováno.

### Řešení

```python
ciste = []

for cislo in [1, 2, 1, 100, 3, 3, 4]:
    if cislo not in ciste:
        ciste.append(cislo)

print(ciste)
```

# Bonusy

## 6 - Přijímačky ◇◇◇◆◆

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

## 7 - Rodná čísla ◇◇◆◆◆

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


Pokud nevíš, jak funguje rodné číslo, vysvětlení je níže:  
Rodné číslo je identifikační číslo, které slouží k jednoznačné identifikaci osoby. V České republice se rodné číslo
skládá z 10 číslic a jednoho lomítka, které ho rozděluje na části.
- Prvních 6 číslic udává datum narození v pořadí rok (2 číslice), měsíc (2 číslice) a den (2 číslice). Například pro
narození 2. února 1990 by prvních 6 číslic mělo být 900202. Zbytek rodného čísla (tj. část za lomítkem) slouží k
identifikaci konkrétní osoby.
- Ženy mají k číslu měsíce přičteno 50, např. 845128/6219 je číslo patřící ženě.*

### Řešení

```python
pocet_muzu = 0
datumy_jako_cislo = []

for rodne_cislo in rodna_cisla:
    ciselne_datum = int(rodne_cislo[:6])
    if int(rodne_cislo[2]) >= 5:  # zena
        ciselne_datum -= 5_000
    else:
        pocet_muzu += 1
    datumy_jako_cislo.append(ciselne_datum)

print(f'přišlo {pocet_muzu} mužů a {len(rodna_cisla) - pocet_muzu} žen')

print(f'nejmladsi se narodil {max(datumy_jako_cislo)}')
print(f'nejstarší se narodil {min(datumy_jako_cislo)}')
```
