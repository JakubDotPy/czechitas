## Výrobci a kategorie

Nyní uvažuj, že si chceme udělat přehled o tom, jaký výrobce produkuje jaké typy potravin. Proveď agregaci
tabulky `food_merged_brands` podle dvou sloupců: `brand_owner` a `branded_food_category`. Sloupce musíš
metodě `food_merged_brands` zadat jako seznam, tj. musíš použít hranaté závorky. Dále vyber sloupec `fdc_id` pro
provedení agregace a použij agregaci `nunique()`, který vrátí počet unikátních hodnot. Nakonec použij
metodu `sort_values` s tím, že chceš data seřadit sestupně.

<details>
<summary><b>Řešení</b></summary>

```python
food_merged_brands.groupby(
    ["brand_owner", "branded_food_category"]
)["fdc_id"].nunique().sort_values(ascending=False)
```

</details>