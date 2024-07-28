## Odstranění duplikátů

Napiš kód, který zpracuje seznam a vytvoří nový seznam bez duplikátů. Výsledné pořadí prvků musí být zachováno.

<details>
<summary><b>Řešení</b></summary>


```python
ciste = []

for cislo in [1, 2, 1, 100, 3, 3, 4]:
    if cislo not in ciste:
        ciste.append(cislo)

print(ciste)
```

</details>
