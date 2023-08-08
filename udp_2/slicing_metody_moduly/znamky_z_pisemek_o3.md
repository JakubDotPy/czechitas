## Známky z písemek ◇◇◆◆◆

Máme data o písemce, která obsahovala 4 otázky. Za každou otázku mohl student (studentka) získat max. 10 bodů.  
Výsledky studentů jsou v následující tabulce.

| Student | Otázka 1 | Otázka 2 | Otázka 3 | Otázka 4 |
|---------|----------|----------|----------|----------|
| A       | 9        | 7        | 8        | 5        |
| B       | 5        | 3        | 6        | 6        |
| C       | 8        | 4        | 9        | 7        |
| D       | 8        | 5        | 4        | 8        |
| E       | 10       | 6        | 10       | 7        |

Ulož si známky studentů do dvourozměrného seznamu.

Spočítej známku jednotlivých studentů. Známku urči podle celkového počtu bodů ze všech příkladů. Bodovací tabulku najdeš
níže.

| Body        | Známka |
|-------------|-------:|
| 36 a více   |      1 |
| 32 a více   |      2 |
| 26 a více   |      3 |
| 20 a více   |      4 |
| méně než 20 |      5 |

Vypočítej průměrné body z jednotlivých otázek. Ze které otázky dostali studenti v průměru nejvíce bodů? A ze které
naopak nejméně?

### Řešení

```python
tabulka_bodu = [
    ['A', 9, 7, 8, 5],
    ['B', 5, 3, 6, 6],
    ['C', 8, 4, 9, 7],
    ['D', 8, 5, 4, 8],
    ['E', 10, 6, 10, 7],
]

body_celkem = []
for student_znamky in tabulka_bodu:
    # rozdlel na studenta a body
    student = student_znamky[0]
    body = student_znamky[1:]

    celkem_bodu = sum(body)

    # urci znamku
    if celkem_bodu < 20:
        znamka = 5
    elif celkem_bodu <= 26:
        znamka = 4
    elif celkem_bodu <= 32:
        znamka = 3
    elif celkem_bodu <= 36:
        znamka = 2
    else:
        znamka = 1

    # vypis
    print(f'student {student} dostal {znamka}')

# Vypočítej průměrné body z jednotlivých otázek.
# Ze které otázky dostali studenti v průměru nejvíce bodů? A ze které naopak nejméně?

# přepíšeme si tabulku
tabulka_po_sloupcich = [
    ['A', 'B', 'C', 'D', 'E'],
    [9, 5, 8, 8, 10],
    [7, 3, 4, 5, 6],
    [8, 6, 9, 4, 10],
    [5, 6, 7, 8, 7],
]

import statistics

prumery = []
for radek in tabulka_po_sloupcich[1:]:
    prumery.append(statistics.mean(radek))

print(prumery)

# z výsledného seznamu je možné vyčíst jednotlivé průměry
```