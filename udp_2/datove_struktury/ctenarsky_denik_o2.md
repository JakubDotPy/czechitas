## Čtenářský deník

Gustav je vášnivým čtenářem detektivek z našeho nakladatelství a navíc si zapisuje knihy, které přečetl.  
Níže ve slovníku vidíme, jaké informace si eviduje - název knihy, počet stran a hodnocení od 0 do 10.

```python
knihy = [
    {'nazev': 'Vražda s příliš mnoha notami', 'pocet_stran': 450, 'hodnoceni': 5},
    {'nazev': 'Vražda podle knihy', 'pocet_stran': 524, 'hodnoceni': 9},
    {'nazev': 'Past', 'pocet_stran': 390, 'hodnoceni': 4},
    {'nazev': 'Popel popelu', 'pocet_stran': 411, 'hodnoceni': 10},
    {'nazev': 'Noc, která mě zabila', 'pocet_stran': 159, 'hodnoceni': 7},
    {'nazev': 'Vražda, kouř a stíny', 'pocet_stran': 258, 'hodnoceni': 6},
    {'nazev': 'Zločinný steh', 'pocet_stran': 542, 'hodnoceni': 8},
    {'nazev': 'Zkus mě chytit', 'pocet_stran': 247, 'hodnoceni': 7},
    {'nazev': 'Vrah zavolá v deset', 'pocet_stran': 396, 'hodnoceni': 6},
]
```

- Napiš program, který spočte celkový počet stran, které Gustav přečetl.
- Připiš do programu výpočet počtu knih, kterým dal Gustav hodnocení alespoň 8.

<details>
<summary><b>Řešení</b></summary>


```python
pocet_stran = 0
for kniha in knihy:
    pocet_stran += kniha['pocet_stran']

# NOTE: nebo lépe
# pocet_stran = sum(kniha['pocet_stran'] for kniha in knihy)

print(f'Přečetl {pocet_stran} stran.')

pocet_nad_osm = 0
for kniha in knihy:
    if kniha['hodnoceni'] >= 8:
        pocet_nad_osm += 1
print(f'Počet knih s hodnocením >= 8: {pocet_nad_osm}')
```

</details>
