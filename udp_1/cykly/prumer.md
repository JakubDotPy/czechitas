## Průměr

Napište cyklus, který projde zadaný seznam desetinných čísel a spočítá jejich průměr. Seznam čísel si vytvořte na
začátku programu.

<details>
<summary><b>Řešení</b></summary>

```python
cisla = [10.5, 13.3, 17.2, 11.5]
soucet = 0
for cislo in cisla:
    soucet += cislo
prumer = soucet / len(cisla)
print(prumer)
```

</details>
