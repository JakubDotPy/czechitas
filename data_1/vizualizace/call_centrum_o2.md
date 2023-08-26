## Call centrum ◇◇◇◆◆

V
souboru [callcentrum.csv](https://kodim.cz/cms/assets/kurzy/python-data-1/python-pro-data-1/vizualizace/excs/excs%3Ecall-centrum/callcentrum.csv)
najdete několik tisíc záznamů pro call centrum, které udávají časy mezi jednotlivými příchozími hovory v minutách a
vteřinách. Načtěte tato data do série v Pythonu. Časy převeďte na vteřiny a zobrazte jejich histogram a boxplot. Co lze
z těchto dvou grafů vyčíst?

K převodu na vteřiny můžeš použít metodu str.split(). Pomocí ní rozdělíš hodnoty minut a vteřin do samostatných sloupců.
Pomocí metody astype(int) převedeš hodnoty na čísla. Poté pomocí počítaných sloupců můžeš spočítat celkový počet vteřin.

<details>
<summary><b>Řešení</b></summary>


```python
import pandas as pd
import matplotlib.pyplot as plt

callcentrum = pd.read_csv("https://kodim.cz/cms/assets/kurzy/python-data-1/python-pro-data-1/vizualizace/excs/excs>call-centrum/callcentrum.csv")
callcentrum = callcentrum["hodnota"].str.split(':', expand=True).astype(int)

callcentrum['seconds'] = callcentrum[0] * 60 + callcentrum[1]

callcentrum.seconds.hist(bins=10)
plt.show()
# většina hovorů je velmi krátká

callcentrum.seconds.plot(kind='box')
plt.show()
# umožňuje nám lepší náhled na celkové rozložení
```

</details>
