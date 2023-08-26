## Studenti ◇◇◆◆◆

Stáhni si datové sety, se kterými budeme pracovat v tomto cvičení: jmena.csv, studenti1.csv, studenti2.csv.

```python
import pandas

jmena = pandas.read_csv("https://kodim.cz/cms/assets/kurzy/python-data-1/python-pro-data-1/agregace-a-spojovani/excs/excs>studenti/jmena.csv")
s1 = pandas.read_csv("https://kodim.cz/cms/assets/kurzy/python-data-1/python-pro-data-1/agregace-a-spojovani/excs/excs>studenti/studenti1.csv")
s2 = pandas.read_csv("https://kodim.cz/cms/assets/kurzy/python-data-1/python-pro-data-1/agregace-a-spojovani/excs/excs>studenti/studenti2.csv")
```

První set už známe z minulé lekce. Druhé dva sety obsahují seznam studentů na nějaké menší IT fakultě. Pozor, tato data
nemají žádnou souvislost s výsledky maturity, které jsme procházeli během lekce.

Proveď následující úkoly a zodpověz předložené otázky.

- Načti dva datové sety studentů do oddělených pandas DataFrame a pomocí funkce concat je spoj do jednoho setu.
- Pokud studentovi chybí ročník, znamená to, že již nestuduje. Pokud mu chybí číslo skupiny, znamená to, že jde o
  dálkového studenta. Kolik studentů v datovém setu již nestuduje a kolik jsou dálkoví studenti?
- Vyčisti data od studentů, kteří nestudují nebo studují jen dálkově. Nadále budeme pracovat pouze s prezenčními
  studenty.
- Zjisti, kolik prezenčních studentů je v každém z oborů.
- Zjisti průměrný prospěch studentů v každém oboru.
- Načti datový set s křestními jmény. Proveď join s tabulkou studentů tak, abychom věděli pohlaví jednotlivých studentů.
- Zjisti, zda na naší fakultě studují IT spíše ženy nebo spíše muži.

<details>
<summary><b>Řešení</b></summary>


```python
import pandas as pd  # zažitý způsob importu pandas

# nacti a spoj studenty
# s1 a s2 nacteme podle zadání
s1 = pd.read_csv("https://kodim.cz/cms/assets/kurzy/python-data-1/python-pro-data-1/agregace-a-spojovani/excs/excs>studenti/studenti1.csv")
s2 = pd.read_csv("https://kodim.cz/cms/assets/kurzy/python-data-1/python-pro-data-1/agregace-a-spojovani/excs/excs>studenti/studenti2.csv")
studenti = pd.concat([s1, s2])

# kolik již nestuduje?
print(sum(studenti["ročník"].isna()))
# dálkoví studenti
print(sum(studenti["kruh"].isna()))

# vyčisti od NaN
studenti = studenti.dropna()

# kolik v každém oboru
print(studenti.groupby('obor')['obor'].count())

# průměrný prospěch po oborech
print(studenti.groupby('obor')['prospěch'].mean())

# načti jména a proveď join
jmena = pd.read_csv("https://kodim.cz/cms/assets/kurzy/python-data-1/python-pro-data-1/agregace-a-spojovani/excs/excs>studenti/jmena.csv")
studenti = pd.merge(studenti, jmena)

# spíše ženy, nebo muži
print(studenti.groupby('pohlaví')['pohlaví'].count())
```

</details>
