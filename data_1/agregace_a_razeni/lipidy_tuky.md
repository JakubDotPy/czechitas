## Lipidy a tuky

Podívej se nyní na to, které kategorie potravin obsahují nejvíce lipidů (tuků). Nejprve pomocí dotazu vytvořit novou
tabulku `food_merged_brands_lipid`, do které pomocí dotazu vlož pouze řádky, které mají jako název výživné látky
hodnotu `Total lipid (fat)`. Poté proveď agregaci podle návu kategorie a seřaď výslednou tabulku tak, aby nahoře byly
vidět kategorie s největším počtem tuků. Porovnej si výslednou tabulku s tabulkou `food_merged_brands_protein_agg`,
kterou jsme vytvořili v rámci lekce. Podívej se, zda se některé kategorie objevují v obou tabulkách.

<details>
<summary><b>Řešení</b></summary>

```python
food_merged_brands_lipid = food_merged_brands[
    food_merged_brands["nutrient_name"] == "Total lipid (fat)"
]

food_merged_brands_lipid_agg = food_merged_brands_lipid.groupby(
    "branded_food_category"
)["amount"].mean()

food_merged_brands_lipid_agg.sort_values(ascending=False)
```

</details>