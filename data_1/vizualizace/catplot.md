## Catplot

Další zajímavý graf, který `seaborn` umí, je `catplot`. Pomocí něj můžeme porovnat obsat výživných látek pro jednotlivé
kategorie potravin. Tvým úkolem bude porovnat obsah proteinů a karbohydrátů pro 12 nejčastějších kategorií.

Vytvoř si pomocí dotazu tabulku, ve které budou informace pouze o proteinech a karbohydrátech. Karbohydráty hledej pod
názvem `Carbohydrate, by difference`. Můžeš je přejmenovat na "Karbohydráty" pomocí metody `replace`.

Dále použij funkci `catplot`. Její použití je velmi podobné ostatním funkcím. Jako první parametr zadej tabulku s daty,
jako parametr `x` sloupeček s názvem kategorie (`branded_food_category`), jako parametr `y` sloupeček `amount` a jako
parametr `hue` sloupeček `nutrition_name`. Alternativně můžeš před vygenerováním grafu sloupeček `nutrition_name`
přejmenovat například na `Výživná látka`, protože bude použit jako nadpis legendy.

Nech si zobrazit graf. Jednotlivé tečky představují hodnoty pro jednotlivé potraviny, každá tečka reprezentuje jednu
potravinu. Barva tečky určuje, o jakou výživnou látku jde. Dále zkus přidat k volání funkce `catplot` parametr `s` s
hodnotou `2` a podívej se, jak se graf změnil. Zkus případně i jiné hodnoty tohoto parametru.

Prohlédni si graf a odpověz na otázky:

1. Pro jakou kategorii platí, že drtivá většina výrobků má více proteinů než karbohydrátů?
1. Pro jakou kategorii platí, že drtivá většina výrobků má více karbohydrátů než proteinů?
1. Existuje nějaká kategorie, kde je na výběr alespoň několik produktů s větším množství karbohydrátů než proteinů, ale
   i několik produktů s větším množstvím proteinů než karbohydrátů?

<details>
<summary><b>Řešení</b></summary>

```python
food_brands_nut["name"] = food_brands_nut["name"].replace(
    "Carbohydrate, by difference", "Karbohydráty"
)
food_top_cat_carb_prot = food_brands_nut[
    food_brands_nut["name"].isin(["Karbohydráty", "Protein"])
]

ax = sns.catplot(
    data=food_top_cat_carb_prot,
    x="branded_food_category",
    y="amount",
    hue="nutrient_name",
    s=2,
)
ax.tick_params(axis="x", rotation=45)
ax._legend.set_title("Výživná látka")


ax.set(
    xlabel="Kategorie",
    ylabel="Množství látky (g)",
    title="Množství výživných látek",
)
```

</details>