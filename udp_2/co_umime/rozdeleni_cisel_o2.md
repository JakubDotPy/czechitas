## Rozdělení čísel

Napiš kód, který zpracuje seznam čísel a vytvoří nový seznam se sudými čísly a nový seznam s lichými čísly z původního
seznamu.

<details>
<summary><b>Řešení</b></summary>


```python
sude = []
liche = []

for cislo in [1, 2, 100, 3, 4]:
    if cislo % 2 == 0:
        sude.append(cislo)
    else:
        liche.append(cislo)

print(sude)
print(liche)
```

</details>
