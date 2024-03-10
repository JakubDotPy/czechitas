## Doprava

Stáhni si data ze
souboru [traffic.csv](https://kodim.cz/cms/assets/czechitas/python-data-1/python-pro-data-1/pivot-tabulky/dalsi-funkce/doprava/traffic.csv),
který zobrazuje počet aut v hodinových intervalech na čtyřech různých křižovatkách.

Pro následující dva úkoly využij funkci `cut`.

- Tabulka je poměrně velká, zkusme tedy rozdělit den na několik částí v závislosti na hodině měření (sloupec `Hour`):
    - noc (22 hodin až 5 hodin),
    - ranní špička (6 hodin až 9 hodin),
    - poledne (10 hodin až 13 hodin),
    - odpolední špička (14 hodin až 16 hodin),
    - večer (17 hodin až 21 hodin).
- Dny v týdnu (sloupec `DayOfWeek`) rozděl na pracovní dny a víkend. Nejprve je třeba se ujistit, které číslo znamená
  který den. Podívej se například první záznam. Tam je datum 2015-11-01, tj 11. listopad 2015. Ve sloupci `DayOfWeek` je
  hodnota 6. Podívej se do kalendáře, který den v týdnu to je. Od jakého čísla jsou dny v týdnu v tabulce počítané?

Nakonec pomocí pivot tabulky průměrné počty aut (sloupec `Vehicles`) v jednotlivých částech dne a typech dne.

Tipy:

- Všimni si, že noc je rozdělená na dvě části - od půlnoci do 5 hodin a od 22 hodin do půlnoci. Bohužel musí být seznam
  názvů skupin unikátní, můžeš ale například vytvořit skupiny `noc_1` a `noc_2`. Poté můžeš podřetězce `_1` a `_2`
  odstranit pomocí metody `.str.replace()`.

<details>
<summary><b>Řešení</b></summary>

```python
# TODO: add solution
```

</details>