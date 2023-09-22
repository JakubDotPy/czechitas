## Dny v měsíci ◇◇◇◇◆

Napište program, který bude mít přímo v kódu zapsaný počet dní v jednotlivých měsících takto:

```python
pocty_dni = [31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31]
```

Nechte váš program vypsat tento seznam do souboru s názvem `kalendar.txt`, každé číslo na jeden řádek.

<details>
<summary><b>Řešení</b></summary>


```python
pocty_dni_text = []
for pocet_dni in pocty_dni:
    pocty_dni_text.append(str(pocet_dni))

with open('kalendar.txt', 'w', encoding='utf-8') as output_file:
    for dny in pocty_dni_text:
        print(dny, file=output_file)
```

</details>
