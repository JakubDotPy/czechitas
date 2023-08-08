## Nabídky práce ◇◇◇◆◆

Stáhni si
soubor [DataAnalyst.csv](https://kodim.cz/cms/assets/kurzy/python-data-1/python-pro-data-1/nacteni-dat/excs/excs%3Enabidky/DataAnalyst.csv)
se seznamem nabídek práce pro datové analytiky.
Soubor byl stažen z webu [Kaggle.com](www.kaggle.com), kde najdeš spoustu zajímavých dat, na kterých se můžeš učit, jak
analyzovat data.

Ale zpět k našim úkolům.

- Načti data do DataFrame, který si pojmenuj jobs.
- Nech si zobrazit názvy sloupců, které jsou v souboru uloženy.
- Podívej se, kolik má soubor řádek.
- Zjisti všechny informace o pracovní pozici na desátém řádku.
- Podívej se, kde budou pracovat zájemci vybraní na dvanáctou až dvacátou pozici.

### Řešení

```python
import pandas as pd

# nacteni dat
jobs = pd.read_csv('DataAnalyst.csv')

# nazvy sloupcu
print(jobs.columns)

# pocet radek
print(jobs.shape[0])

# info o pozici na desatem radku
print(jobs.iloc[9])

# kde pracuji vybraní na dvanáctou až dvacátou pozici
print(jobs.iloc[10:12, 5])
```