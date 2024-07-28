## Recepty

Pohlédněte na následující reprezentaci receptu:

```python
{
    'nazev'      : 'Batáty se šalvějí a pancettou',
    'narocnost'  : 'stredni',
    'doba'       : 30,
    'ingredience': [
        ['batát', '1', '15 kč'],
        ['olivový olej', '2 lžíce', '2 kč'],
        ['pancetta', '4-6 plátků', '21 kč'],
        ['přepuštěné máslo', '2 lžíce', '5 kč'],
        ['mletý černý pepř', '1/2 lžičky', '0.5 kč'],
        ['sůl', '1/2 lžičky', '0.1 kč'],
        ['muškátový oříšek', 'špetka', '1 kč'],
        ['česnek', '2 stroužky', '1 kč'],
        ['šalvějové lístky', '20-25', '12 kč']
    ]
}
```

Uložte si tuto strukturu do proměnné `recept` na začátek nového programu. Vypište pomocí funkce `print` kolik bude celé
jídlo stát korun zaokrouhlené na celé koruny nahoru.

<details>
<summary><b>Řešení</b></summary>

```python
recept = {
    'nazev'      : 'Batáty se šalvějí a pancettou',
    'narocnost'  : 'stredni',
    'doba'       : 30,
    'ingredience': [
        ['batát', '1', '15 kč'],
        ['olivový olej', '2 lžíce', '2 kč'],
        ['pancetta', '4-6 plátků', '21 kč'],
        ['přepuštěné máslo', '2 lžíce', '5 kč'],
        ['mletý černý pepř', '1/2 lžičky', '0.5 kč'],
        ['sůl', '1/2 lžičky', '0.1 kč'],
        ['muškátový oříšek', 'špetka', '1 kč'],
        ['česnek', '2 stroužky', '1 kč'],
        ['šalvějové lístky', '20-25', '12 kč']
    ]
}

celkem = 0
for ingredience in recept['ingredience']:
    cena_text = ingredience[-1]
    cena = float(cena_text.split(' ')[0])
    celkem += cena

print(f'recept stojí celkem {celkem} Kč')
```

</details>
