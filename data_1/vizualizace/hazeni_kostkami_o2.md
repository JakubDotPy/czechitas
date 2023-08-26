## Házení kostkami ◇◇◇◆◆

Mějme dvě
hrací [kostky](https://kodim.cz/cms/assets/kurzy/python-data-1/python-pro-data-1/vizualizace/excs/excs%3Ehazeni-kostkami/kostky.csv)
, kterými vždy hodíme najednou a zaznamenáme součet bodů. Stáhněte si textový soubor kostky.csv, který obsahuje 1000
takových nezávislých hodů.

Načtěte tato data do tabulky a zobrazte histogram hodů. Zvolte vhodné rozložení přihrádek a zodpovězte následující
dotazy:

- Jaká je nejčastější hodnota, která na dvou kostkách padne?
- Je větší šance, že padne hodnota 12 než že padne hodnota 2?

<details>
<summary><b>Řešení</b></summary>


```python
import pandas as pd
import matplotlib.pyplot as plt

kostky = pd.read_csv("https://kodim.cz/cms/assets/kurzy/python-data-1/python-pro-data-1/vizualizace/excs/excs>hazeni-kostkami/kostky.csv")

# histogram
kostky.hist(bins=range(2, 14))
plt.show()
# nejčastější tak je 7
# častěji padne 12
```

</details>
