## Dvě kritéria

Připravujeme seznam potravin pro účely lékařského výzkumu, který se bude zabývat kardiovaskulárním systémem. Chceme
vybrat potraviny, které splňují dvě kritéria:

- nízký obsah nasycených mastných kyselin (`"Fatty acids, total saturated"`, uvažuj méně než 1 gram),
- vysoký obsah vlákniny (`"Fiber, total dietary"`, uvažuj více než 5 gramů).

Zatímco nasycené mastné kyseliny jsou považovány za spíše škodlivé pro kardiovaskulární systém, vláknina je považována
spíše za prospěšnou.

Nejprve je potřeba napsat dotaz, který potraviny vybere. Dotaz je poměrně složitý,
ale později si v rámci kurzu ukážeme, jak takovou úlohu vyřešit jednodušeji.
Je potřeba použít operátor `&` i `|` a závorky, pomocí kterých řídíme, které podmínky se vyhodnocují spolu. Níže jsou
rozepsané podmínky, které budeme potřebovat:

- Ve sloupci `"name"` musí být hodnota `"Fatty acids, total saturated"` a současně ve sloupci `"amount"` hodnota menší
  než 1. Mezi tyto podmínky vložíme operátor `&`, protože musí být splněné obě.
- Ve sloupci `"name"` musí být hodnota `"Fiber, total dietary"` a současně ve sloupci `"amount"` hodnota vetší než 4.
  Mezi tyto podmínky vložíme operátor `&`, protože musí být splněné obě.

Protože obě výživné látky jsou na samostatném řádku, musíme mezi obě podmínky dát operátor `|`. Pokud nějaká potraviny
splňuje obě podmínky, bude tedy ve výsledné tabulce dvakrát. Pokud splňuje pouze jednou z podmínek, bude ve výsledné
tabulce pouze jednou. Počet výskytů potraviny ve výsledné tabulce můžeme ověřit pomocí metodu `values_count()`.

U kombinace operátorů `&` a `|` je vhodné uvědomit si, v jaké prioritě by měly být používány. Ač to zní složitě, je to
pojem, který už známe z úvodního kurzu z příkladu, kde jsme používali násobení a sčítání v jednom příkladu. Pro
operátory `&` a `|` platí, že operátor & máš vyšší prioritu než `|`. To nám vyhovuje, protože my chceme nejprve
vyhodnotit podmínky s operátorem `&` a poté spojit výsledky s využitím opretáro `|`.

Níže je tedy struktura, kterou je potřeba upravit, aby řešila popsané podmínky.

> food_nutrient_filtered = food_nutrient[(ve sloupci "name" je hodnota "Fatty acids, total saturated") 
> & (ve sloupci "amount" je hodnota menší než 1) | (ve sloupci "name" je hodnota "Fiber, total dietary") 
> & (ve sloupci "amount" je hodnota větší než 4)]

Pokud se úvaze o priotách chceš vyhnout, je možné to vyřešit přidanými závorkami. Tyto závorky nijak neovlivňují, jak
Python příkaz vyhodnotí, ale můžou zlepšit čistelnost a pochopitelnost příkazu pro člověka.

> food_nutrient_filtered = food_nutrient[((ve sloupci "name" je hodnota "Fatty acids, total saturated") & (ve sloupci "
> amount" je hodnota menší než 1)) | ((ve sloupci "name" je hodnota "Fiber, total dietary") &

<details>
<summary><b>Řešení</b></summary>

```python
import pandas as pd

url_food_nutrient = "https://kodim.cz/cms/assets/czechitas/python-data-1/python-pro-data-1/podmineny-vyber/podmineny-vyber/food_nutrient.csv"
food_nutrient = pd.read_csv(url_food_nutrient)

food_nutrient_filtered = food_nutrient[
    ((food_nutrient["name"] == "Fatty acids, total saturated") & (food_nutrient["amount"] < 1))
    | ((food_nutrient["name"] == "Fiber, total dietary") & (food_nutrient["amount"] > 5))
]

# nebo
food_nutrient_filtered = food_nutrient[
    (food_nutrient["name"] == "Fatty acids, total saturated")
    & (food_nutrient["amount"] < 1)
    | (food_nutrient["name"] == "Fiber, total dietary")
    & (food_nutrient["amount"] > 4)
]

food_nutrient_filtered["name"].value_counts()
```

</details>