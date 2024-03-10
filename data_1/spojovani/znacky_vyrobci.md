## Značky a výrobci

Stáhni si data z
tabulky [branded_food.csv](https://kodim.cz/cms/assets/czechitas/python-data-1/python-pro-data-1/spojovani/excs/znacky/branded_food.csv),
která obsahuje data o konkrétních potravinách od výrobců. Tabulku načti do `pandas` tabulky `branded_food`.

Pro tabulku `branded_food` splň následující úkoly.

- Zobraz si prvních několik řádků tabulky a podívej se na to, jaké jsou v ní sloupce a jaké jsou v nich hodnoty.
- Ve sloupci `brand_owner` jsou názvy výrobců potravin. Zjisti tři výrobce s největším počtem potravin v tabulce.
- Ve sloupci `branded_food_category` jsou kategorie potravin. Zjisti pět kategorií s největších počtem potravin v
  tabulce.

Nápověda: Na body 2 a 3 využij metodu, kterou jsme si již ukazovali v předchozí lekci. Její název se skládá ze dvou
slov - anglického výrazu pro hodnotu a pro počet.

V tabulce je sloupec `fdc_id`, pomocí kterého ji můžeš propojit s tabulkou `food_merged`. Protože názvy jsou v obou
tabulkách stejné, takže by bylo možné použít parametr `on`. Vyzkoušej si ale místo toho parametry `left_on`
a `right_on`, kterým dáš stejnou hodnotu, tj. název sloupce `fdc_id`. Výsledek ulož do tabulky `food_merged_brands`.

Pro tabulku `food_merged_brands` splň následující úkoly.

- U výsledné tabulky `food_merged_brands` zkontroluj počet řádků a srovnej ho s původní tabulkou `food_merged`. Ubyly
  nějaké řádky? A čím to je?
- Nyní proveď operaci `merge` znovu, ale s parametrem `how` nastaveným na hodnotu `left`. Zkontroluj počet řádků a
  porovnej ho s počtem řádků tabulky `food_merged_brands`. Proč se počet liší?

<details>
<summary><b>Řešení</b></summary>

```python
import pandas as pd

url_branded_food = "https://kodim.cz/cms/assets/czechitas/python-data-1/python-pro-data-1/spojovani/excs/znacky/branded_food.csv"
branded_food = pd.read_csv(url_branded_food)

# Zobraz si prvních několik řádků tabulky a podívej se na to, jaké jsou v ní sloupce a jaké jsou v nich hodnoty.
print(branded_food.head(2))

# Ve sloupci brand_owner jsou názvy výrobců potravin. Zjisti tři výrobce s největším počtem potravin v tabulce.
print(branded_food['brand_owner'].value_counts().head(3))

# Ve sloupci branded_food_category jsou kategorie potravin. Zjisti pět kategorií s největších počtem potravin v tabulce.
print(branded_food['branded_food_category'].value_counts().head(5))


food_merged_brands = pd.merge(food_merged, branded_food, right_on="fdc_id", left_on="fdc_id")

# U výsledné tabulky food_merged_brands zkontroluj počet řádků a srovnej ho s původní tabulkou food_merged.
# Ubyly nějaké řádky? A čím to je?
print(food_merged_brands.shape)
print(food_merged.shape)

# Nyní proveď operaci merge znovu, ale s parametrem how nastaveným na hodnotu left. 
# Zkontroluj počet řádků a porovnej ho s počtem řádků tabulky food_merged_brands. Proč se počet liší?
food_merged_brands = pd.merge(food_merged, branded_food, right_on="fdc_id", left_on="fdc_id", how="left")
print(food_merged_brands.shape)
print(food_merged.shape)
```

</details>