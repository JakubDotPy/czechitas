## Přijímačky ◇◇◇◆◆

Vrať se k příkladu vysvědčení studenta.

```python
school_report = [
    ['Český jazyk', 1],
    ['Anglický jazyk', 1],
    ['Matematika', 1],
    ['Přírodopis', 2],
    ['Dějepis', 1],
    ['Fyzika', 2],
    ['Hudební výchova', 4],
    ['Výtvarná výchova', 2],
    ['Tělesná výchova', 3],
    ['Chemie', 4],
]
```

Při přihlašování na střední školu mohou být důležitější příklady z některých konkrétních předmětů. Uprav kód z lekce
tak, aby spočítal průměr pouze z jazyků, matematiky a fyziky.

<details>
<summary><b>Řešení</b></summary>


```python

sledovane_predmety = [
    'Český jazyk',
    'Anglický jazyk',
    'Matematika',
    'Fyzika',
]

soucet = 0
for predmet_znamka in school_report:
    # rozdelime si dvojici na dve samostatne promenne pro lepsi praci
    predmet = predmet_znamka[0]
    znamka = predmet_znamka[1]
    if predmet in sledovane_predmety:
        soucet += znamka

print(f'Průměr sledovaných předmětů je: {soucet / len(sledovane_predmety)}')
```

</details>
