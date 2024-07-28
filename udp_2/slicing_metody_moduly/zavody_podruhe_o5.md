## Závody podruhé

Zadání je podobné jako u předchozího příkladu, ale nyní zkusíme výpočet provést pro všechny závodníky.

- Nejprve (pomocí cyklu a metody `append()`) vytvoř dvourozměrný seznam, kde na nulté pozici vnořeného seznamu je číslo
  běžce a na první pozici je čas běžce v minutách jako desetinné číslo.
- Ve druhém kroku (opět pomocí cyklu a metody `append()`) vytvoř další dvourozměrný seznam, kde na nulté pozici
  vnořeného seznamu je číslo běžce a na první pozici je rozdíl času běžce oproti času vítěze v minutách. Jinak řečeno,
  bude tam číslo, které udává, o kolik by běžec musel být rychlejší, aby závod vyhrál.

<details>
<summary><b>Řešení</b></summary>


```python
vysledky = [
    ["Brunner Radek", [3, 0, 9]],
    ["Urban Jaroslav", [3, 11, 44]],
    ["Andrle Jakub", [3, 12, 21]],
    ["Fiala Stanislav", [3, 13, 31]]
]

# použijeme funkci enumerate, dostaneme tak zároveň i pozici v seznamu
# https://docs.python.org/3/library/functions.html#enumerate

casy = []

for pozice, data in enumerate(vysledky, start=1):
    cas_v_minutach = data[1][0] * 60 + data[1][1] + data[1][2] / 60
    casy.append([pozice, cas_v_minutach])

print(casy)

vitezny_cas = vysledky[0][1][0] * 60 + vysledky[0][1][1] + vysledky[0][1][2] / 60

rozdily = []

for pozice, data in enumerate(vysledky, start=1):
    cas_v_minutach = data[1][0] * 60 + data[1][1] + data[1][2] / 60
    rozdily.append([pozice, cas_v_minutach - vitezny_cas])

print(rozdily)
```


</details>
