# Cvičení

## 1 - Česká jména 2 ◇◇◆◆◆

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