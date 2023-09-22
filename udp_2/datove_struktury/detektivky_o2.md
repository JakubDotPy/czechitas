## Detektivky ◇◇◇◆◆

Vydavatel detektivek si eviduje prodané kusy u jednotlivých knih.  
V následujícím slovníku najdeš tři knihy a u každé z nich je počet prodaných kusů.

```python
prodano = {
    'Zkus mě chytit'     : 4165,
    'Vrah zavolá v deset': 5681,
    'Zločinný steh'      : 2565,
}
```

- Zkopíruj si slovník do svého programu.
- Přidej do slovníku nově vydanou detektivku `"Noc, která mě zabila"`, která zatím nebyla uvedena na trh, je tedy
  prodáno
  `0` kusů.
- U knihy `"Vrah zavolá v deset"` zvyš počet prodaných kusů o `100`.

<details>
<summary><b>Řešení</b></summary>


```python
prodano['Noc, která mě zabila'] = 0

prodano['Vrah zavolá v deset'] += 100
```

</details>
