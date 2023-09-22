## Čísla jako text ◇◇◇◆◆

Mějme seznam čísel zadaných jako text

```python
hodnoty = ['12', '1', '7', '-11']
```

Potřebujeme k třetímu číslu v seznamu přičíst 4, aby výsledek vypadal takto:

```python
hodnoty = ['12', '1', '11', '-11']
```

Před tím, než se podíváte na následující kroky, sami si rozmyslete postup, jak toto provést. Až když si nejste jistí,
pokračujte podle následujících kroků.

- Uložte si hodnotu na třetí pozici v seznamu do nějaké proměnné.
- Převeďte tuto hodnotu na číslo a přičtěte k němu 4. Výsledek uložte do proměnné `vysledek`.
- Převeďte hodnotu v proměnné `vysledek` zpět na řetězec a uložte ji na třetí pozici v seznamu `hodnoty`.

<details>
<summary><b>Řešení</b></summary>


```python
hodnoty = ['12', '1', '7', '-11']

treti = hodnoty[2]
vysledek = int(treti) + 4
hodnoty[2] = vysledek
```

</details>
