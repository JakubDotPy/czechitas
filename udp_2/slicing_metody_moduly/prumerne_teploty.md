## Průměrné teploty

Následující tabulka obsahuje průměrné roční teploty v České republice za roky 2001 až 2010 (zdroj: Český
hydrometeorologický ústav).

| rok  | teplota °C |
|------|:----------:|
| 2001 |    7.8     |
| 2002 |    8.7     |
| 2003 |    8.2     |
| 2004 |    7.8     |
| 2005 |    7.7     |
| 2006 |    8.2     |
| 2007 |    9.1     |
| 2008 |    8.9     |
| 2009 |    8.4     |
| 2010 |    7.2     |

Vytvořte reprezentaci této tabulky pomocí seznamu seznamů. Zde existují dvě možnosti.  
Nejprve vytvořte seznam, který obsahuje řádky tabulky jako dvouprvkové seznamy a uložte jej do proměnné `radky`.  
Poté vytvořte seznam, který obsahuje sloupce tabulky, tedy dva seznamy po deseti prvcích. Uložte jej do
proměnné `sloupce`.

Pro obě tyto reprezentace vyřešte následující úkoly

- Získejte teplotu na třetím řádku tabulky.
- Získejte rok na pátém řádku tabulky.
- Získejte poslední řádek tabulky jako seznam.
- Vytvořte tabulku bez prvních dvou řádků.
- Vytvořte tabulku pouze z prvních dvou řádků.
- Vytvořte tabulku obsahující jen řádky 5, 6, 7, 8 (myšleno při "lidském" číslování, tj. od 1).
- Použitím proměnné `sloupce` vypište seznam teplot seřazený vzestupně podle velikosti. Šlo by to i pomocí
  proměnné `radky`, ale to ještě neumíme.

<details>
<summary><b>Řešení</b></summary>

```python
radky = [
    [2001, 7.8],
    [2002, 8.7],
    [2003, 8.2],
    [2004, 7.8],
    [2005, 7.7],
    [2006, 8.2],
    [2007, 9.1],
    [2008, 8.9],
    [2009, 8.4],
    [2010, 7.2],
]

# Získejte teplotu na třetím řádku tabulky.
radky[2][1]

# Získejte rok na pátém řádku tabulky.
radky[4][0]

# Získejte poslední řádek tabulky jako seznam.
radky[-1]

# Vytvořte tabulku bez prvních dvou řádků.
radky[2:]

# Vytvořte tabulku pouze z prvních dvou řádků.
radky[:2]

# Vytvořte tabulku obsahující jen řádky 5, 6, 7, 8 (myšleno při "lidském" číslování, tj. od 1).
radky[4:8]

sloupce = [
    [2001, 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010],
    [7.8, 8.7, 8.2, 7.8, 7.7, 8.2, 9.1, 8.9, 8.4, 7.2],
]

# Použitím proměnné sloupce vypište seznam teplot seřazený vzestupně podle velikosti.
print(sorted(sloupce[1]))
```

</details>
