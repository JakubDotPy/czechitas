## Titanic data set

Každý tutoriál datové analýzy začíná zpracováváním data setu pasažérů lodi Titanic.  
Nebude tomu jinak ani v našem případě. Stáhni si soubor [titanic.csv](https://kodim.cz/cms/assets/analyza-dat/python-data-1/python-pro-data-1/nacteni-dat/excs/titanic/titanic.csv).

- Načti data do DataFrame, který si pojmenuj titanic.
- Nech si zobrazit názvy sloupců, které jsou v souboru uloženy.
- Podívej se, kolik má soubor řádků.
- Zjisti, v jakých sloupcích nějaké hodnoty chybí.

<details>
<summary><b>Řešení</b></summary>

```python
import pandas as pd

# nactecni dat
titanic = pd.read_csv('titanic.csv')

# zobrazeni sloupcu
print(titanic.columns)

# pocet radku
print(titanic.shape[0])

# chybejici hodnoty zjistíme ze sloupce "Non-Null Count"
print(titanic.info())
```

</details>