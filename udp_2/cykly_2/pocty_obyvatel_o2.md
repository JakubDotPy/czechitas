## Počty obyvatel

Mějme počty obyvatel v jednotlivých krajích ČR podle následující tabulky.

| Kraj                 | Počet obyvatel |
|----------------------|----------------|
| Hlavní město Praha   | 1 280 508      |
| Jihočeský kraj       | 638 782        |
| Jihomoravský kraj    | 1 178 812      |
| Karlovarský kraj     | 296 749        |
| Kraj Vysočina        | 508 952        |
| Královéhradecký kraj | 550 804        |
| Liberecký kraj       | 440 636        |
| Moravskoslezský kraj | 1 209 879      |
| Olomoucký kraj       | 633 925        |
| Pardubický kraj      | 517 087        |
| Plzeňský kraj        | 578 629        |
| Středočeský kraj     | 1 338 982      |
| Ústecký kraj         | 821 377        |
| Zlínský kraj         | 583 698        |

Tuto tabulku máme reprezentovanou jako seznam:

```python
kraje = [
    ['Hlavní město Praha', '1 280 508'],
    ['Jihočeský kraj', '638 782'],
    ['Jihomoravský kraj', '1 178 812'],
    ['Karlovarský kraj', '296 749'],
    ['Kraj Vysočina', '508 952'],
    ['Královéhradecký kraj', '550 804'],
    ['Liberecký kraj', '440 636'],
    ['Moravskoslezský kraj', '1 209 879'],
    ['Olomoucký kraj', '633 925'],
    ['Pardubický kraj', '517 087'],
    ['Plzeňský kraj', '578 629'],
    ['Středočeský kraj', '1 338 982'],
    ['Ústecký kraj', '821 377'],
    ['Zlínský kraj', '583 698']
]
```

- Vytvořte seznam, který obsahuje pouze názvy všech krajů, tedy první sloupeček této tabulky.
- Vytvořte seznam, který obsahuje počty obyvatel jako čísla. Pro zbavení se mezer v číslech se vám jistě bude hodit
  metoda řetězců jménem replace().
- Do vhodně pojmenované proměnné uložte seznam, který reprezentuje výše uvedenou tabulku jako dva seznamy: seznam jmen a
  seznam počtů obyvatel jako čísla.

<details>
<summary><b>Řešení</b></summary>


```python
nazvy = [kraj[0] for kraj in kraje]
obyvatele = [int(kraj[-1].replace(' ', '')) for kraj in kraje]

jmena_a_pocty = [
  [kraj[0] for kraj in kraje],
  [int(kraj[-1].replace(' ', '')) for kraj in kraje],
]
```

</details>
