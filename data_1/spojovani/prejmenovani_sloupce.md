## Přejmenování sloupce

Čím více tabulky propojujeme, tím více sloupců v nich máme. To může být časem až matoucí. Například máme v tabulce
sloupec `name`, který označuje název výživné látky. Pro větší přehlednost ho přejmenujme na `nutrient_name`. K tomu
slouží metoda `rename`. Níže je příklad toho, jak lze metodu použít. Pozorně si ho prohlédni. Metodu voláme pomocí
tečkové notace, kterou už jsme využívali. Dále je potřeba zapsat název parametru (`columns`, protože chceme přejmenovat
sloupce). Jako hodnotu vkládáme strukturu, která je označováno jako **slovník**. Jedná se o dvojici hodnot ve složených
závorkách, která je oddělená dvojtečkou. Před dvojtečkou je starý název sloupce (v našem případě to bude `name`) a za
dvojtečkou nový název sloupce (v našem případě to bude `nutrition_name`). Uprav tedy použití metody a spusť ho. Následně
zkontroluj výsledek pomocí `.columns`.

```py
food_merged_brands = food_merged_brands.rename(columns={"stary_nazev": "novy_nazev"})
```

Jako bonus se zamysli nad tím, co by se mohlo stát, pokud na místo starého názvu zadáš sloupec, který v tabulce není (
např. `test`). Jaké chování bys od metody očekával(a)? Jakmile to budeš mít rozmyšlené, použij metodu s neexistujícím
názvem sloupce a zkontroluj, co se stalo.

<details>
<summary><b>Řešení</b></summary>

```python
food_merged_brands = food_merged_brands.rename(columns={"name": "nutrient_name"})
```

</details>