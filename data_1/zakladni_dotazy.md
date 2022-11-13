# Cvičení

## 1 - Česká jména ○○○♦♦

Stáhni si
soubor [jmena.csv](https://kodim.cz/cms/assets/kurzy/python-data-1/python-pro-data-1/zakladni-dotazy/excs/excs%3Eceska-jmena/jmena.csv)
,
který obsahuje tabulku 100 nejpoužívanějších českých křestních jmen seřazených od nejpoužívanějšího k nejméně
používanému.  
Pomocí Pandas načti tuto tabulku jako DataFrame. Jako index zvol sloupec s názvem `'jméno'`.

Datový soubor obsahuje následující sloupečky

**jméno** - křestní jméno  
**četnost** - počet obyvatel ČR mající toto jméno  
**věk** - průměrný věk nositelů jména  
**pohlaví** - zda je jméno mužské či ženské  
**svátek** - datum, kdy má dané jméno svátek  
**původ** - původ jména

Vyřešte následující úkoly.

- Vypište na konzoli informace o jménu Jiří.
- Vypište na konzoli informace pro jména Martin, Zuzana a Josef.
- Vypište na konzoli informace o všech nejčastějších jménech až po Martina.
- Vypište pouze průměrné věky osob mající jména mezi Martinem a Terezou.
- Vypište průměrný věk a původ pro všechna jména od Libora dolů.
- Vypište sloupečky mezi věkem a původem pro všechna jména v tabulce.

### Řešení

```python
import pandas as pd

jmena = pd.read_csv('jmena.csv')
jmena = jmena.set_index('jméno')

# Jiří
print(jmena.loc['Jiří'])

# Martin, Zuzana, Josef
print(jmena.loc[['Martin', 'Zuzana', 'Josef']])

# četnost po Martina
print(jmena.loc[:'Martin'])

# věk Martin až Tereza
print(jmena.loc['Martin':'Tereza', 'věk'])

# věk a původ od Libora dolů
print(jmena.loc['Libor':, ['věk', 'původ']])

# vše mezi věkem a původem
print(jmena.loc[:, 'věk':'původ'])
```

## 2 - Česká jména ○○♦♦♦

Stáhni si
soubor [jmena.csv](https://kodim.cz/cms/assets/kurzy/python-data-1/python-pro-data-1/zakladni-dotazy/excs/excs%3Eceska-jmena/jmena.csv)
se jmény a načti ho tak, aby Pandas vyrobil číselný index.  
Proveď následující dotazy:

- Vypiš všechny řádky se jmény, jejichž nositelé mají průměrný věk vyšší než 60.
- Vypiš pouze jména z těch řádků, kde četnost je mezi 80 000 a 100 000.
- Vypiš jména a četnost pro jména se slovanským nebo hebrejským původem. Kolik takových jmen je?
- Vypiš všechna jména, která mají svátek první 3 dny v prosinci.

### Řešení

```python
import pandas as pd

jmena = pd.read_csv('jmena.csv')

# jména věk vyšší 60
print(jmena[jmena['věk'] > 60])

# jména četnost 80_000 - 100_000
print(jmena[(jmena['četnost'] > 80_000) & (jmena['četnost'] < 100_000)])

# slovanska hebrejska
slovanska_a_hebrejska = jmena[jmena['původ'].isin(['slovanský', 'hebrejský'])]
print(slovanska_a_hebrejska)
print(len(slovanska_a_hebrejska))

# svatek prvni tri dny v prosinci
print(jmena[jmena['svátek'].isin(['1.12', '2.12', '3.12'])])
```