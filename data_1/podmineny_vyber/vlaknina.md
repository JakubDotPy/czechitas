## vláknina

Problémem dnešních potravin je často nedostatek vlákniny.  
Konzumace potravin bohatých na vlákninu může být pro řadu lidí zdravotně prospěná.  
Vyhledej v tabulce `food_nutrient` potraviny, které obsahují alespoň 10 gramů vlákniny.  
Vláknina je uložená pod názvem `Fiber, total dietary`. Napiš dotaz jako jeden příkaz a využij operátor `&`.

<details>
<summary><b>Řešení</b></summary>

```python
import pandas as pd

url_food_nutrient = "https://kodim.cz/cms/assets/czechitas/python-data-1/python-pro-data-1/podmineny-vyber/podmineny-vyber/food_nutrient.csv"
food_nutrient = pd.read_csv(url_food_nutrient)

with_fiber= food_nutrient[
    (food_nutrient["name"] == "Fiber, total dietary")
    & (food_nutrient["amount"] >= 10)
]

print(with_fiber)
```

</details>