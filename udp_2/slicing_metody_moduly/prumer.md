## Průměr

Mějme proměnnou `s`, ve které předpokládáme uložený nějaký seznam.  
Sestavte v výraz (vzoreček), který spočítá průměrnou hodnotu v takovém seznamu. Otestujte jej na seznamech různých
délek.

<details>
<summary><b>Řešení</b></summary>

```python
s = [1, 2, 3, 5, 8, 15, 56]
prumer = sum(s) / len(s)
print(f'prumer {s} je {prumer}')
```

</details>
