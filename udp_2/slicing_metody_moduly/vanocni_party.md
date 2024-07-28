## Vánoční párty

Ve statistice existuje ukazatel zvaný _modus_, který vrátí nejčastější hodnotu v datech. V modulu `statistics` existuje
funkce `mode()`, která umí modus spočítat. Funkce `mode()` má navíc vychytávku, umí pracovat i s řetězci.

Uvažuj data v seznamu `votes`, což je hlasování zaměstnanců malé firmy o tom, jakou akci podniknou během jejich
vánočního večírku. Použij funkce `mode()` ke zjištění, pro jakou aktivitu hlasovalo nejvíce zaměstnanců. Funkce má jeden
parametr - seznam, ze kterého má určit nejčastější prvek.

<details>
<summary><b>Řešení</b></summary>

```python
import statistics

votes = [
    "curling",
    "vánoční svařák na trzích",
    "vánoční svařák na trzích",
    "curling",
    "zážitková první pomoc",
    "curling",
    "zážitková první pomoc",
    "curling",
    "zážitková první pomoc",
]

print(f'nejčastější volbou bylo: {statistics.mode(votes)}')
```

</details>
