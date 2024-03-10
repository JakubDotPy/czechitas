## Česká jména

Stáhni si soubor [jmena.csv](https://kodim.cz/cms/assets/czechitas/python-data-1/python-pro-data-1/podmineny-vyber/podmineny-vyber/ceska-jmena/jmena.csv), která obsahuje nejpoužívanější česká jména.

- Vypiš všechny řádky se jmény, jejichž nositelé mají průměrný věk vyšší než 60 (hodnota ve sloupci `prumerny_vek` je větší než 60).
- Vypiš pouze jména z těch řádků, kde četnost je mezi 80 000 a 100 000.
- Vypiš jména a četnost pro jména se slovanským nebo hebrejským původem. Kolik takových jmen je?

Pro poslední úkol můžeš využít operátor `|`. Alternativně si můžeš vyzkoušet metodu `.isin()`, která zápis zkrátí. 
Jako parametr vkládáme seznam hodnot, které vyhovují podmínce. Níže je příklad použití metody.  
Z tabulky `tabulka` chceme vybrat řádky, které ve sloupci `sloupec` mají hodnotu `hodnota_1` nebo `hodnota_2`. 
Pokud jsi vytvořil(a) i verzi s operátorem `|`, můžeš obě verze porovnat a rozhodnout se, která verze se ti líbí více.

`tabulka = tabulka[tabulka["sloupec"].isin(["hodnota_1", "hodnota_2"])]`

<details>
<summary><b>Řešení</b></summary>

```python
import pandas as pd

url = "https://kodim.cz/cms/assets/czechitas/python-data-1/python-pro-data-1/podmineny-vyber/podmineny-vyber/ceska-jmena/jmena.csv"
jmena = pd.read_csv(url)

# Vypiš všechny řádky se jmény, jejichž nositelé mají průměrný věk vyšší než 60.
print(jmena[jmena["prumerny_vek"] > 60])

# Vypiš pouze jména z těch řádků, kde četnost je mezi 80 000 a 100 000.
print(jmena[(jmena["cetnost"] >= 80_000) & (jmena["cetnost"] <= 100_000)])

# Slovanský nebo Hebrejský původ
print(jmena[(jmena["puvod"] == "slovanský") | (jmena["puvod"] == "hebrejský")])
# jmena[jmena["puvod"].isin(["slovanský", "hebrejský"])]
```

</details>