## Odstín

V rámci lekce jsme porovnávali množství proteinů a lipidů (tuků) v energetických tyčinkách. Potřebná data máme v
tabulce `food_merged_brands`. Podobné srování můžeme udělat i s využitím histogramu. Použij funkci histogram pro
tabulku `food_merged_brands_box`. Abys dokázal(a) rozlišit mezi oběma výživnými látkami, použij parametr `hue`, kterému
zadáš jako hodnotu `nutrient_name`. Díky tomu bude mít každá výživná látka samostatný sloupec se svojí barvou. Dále
použij funkci `range`, tentokrát ale rozděl hodnoty po pěti, tj. hranice intervalů budou 0, 5, 10, 15 atd. Zobraz si
výsledný graf. Protože toto zobrazení může být poněkud nepřehledné, vyzkoušej ještě přidat parametr `multiple` s
hodnotou `stack`.

<details>
<summary><b>Řešení</b></summary>

```python
ax = sns.histplot(
    food_merged_brands_box,
    x="amount",
    bins=range(0, 110, 5),
    hue="nutrient_name",
    multiple="stack",
)

ax.set(
    xlabel="Množství výživných látek",
    ylabel="Počet potravin",
    title="Množství proteinu v potravinách",
)
```

</details>
