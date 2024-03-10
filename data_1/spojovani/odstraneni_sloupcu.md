## Odstranění sloupců

Pokud máme v tabulce zbytečné sloupce, můžeme je odstranit. Zbytečných sloupců se můžeme zbavit dvě způsoby:

1. Výběrem sloupců, které v tabulce *chceme*. To už jsme si ukazovali v předchozí lekci v části "Výběr sloupců".
1. Odebráním sloupců, které v tabulce *nechceme*. K tomu slouží metoda `drop()`.

Níže je příklad použití metody `drop()`. Použijeme parametr `columns`, kterému zadáme seznam sloupců k odstranění.

```py
food_merged_brands = food_merged_brands.drop(columns=["sloupec_1", "sloupec_2"])
```

Využij metodu k odstranění sloupců `footnote` a `min_year_acquired`. Pomocí vlastnosti `.columns` zkontroluj výsledek.
Nakonec se podobně jako v předchozím cvičení zamysli nad tím, co by se mohlo stát, kdybys do seznamu vložila
neexistující název sloupce, například `test`. Poté metodu `drop()` s neexistujícím názvem sloupce vyzkoušej. Překvapil
tě výsledek?

<details>
<summary><b>Řešení</b></summary>

```python
food_merged_brands = food_merged_brands.drop(columns=["footnote", "min_year_acquired"])

print(food_merged_brands.columns)
```

</details>
