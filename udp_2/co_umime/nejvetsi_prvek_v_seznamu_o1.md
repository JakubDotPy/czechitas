## Největší prvek v seznamu

Napiš kód, který zpracuje seznam čísel a vypíše největší prvek v tomto seznamu (bez použití funkce `max()`).

<details>
<summary><b>Řešení</b></summary>


```python
nejvetsi = 0

for cislo in [1, 2, 100, 3, 4]:
    if cislo > nejvetsi:
        nejvetsi = cislo

print(nejvetsi)
```

</details>
