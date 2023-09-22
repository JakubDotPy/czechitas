## Seznamy čísel ◇◇◇◇◆

Mějme zadaný následující seznam

```python
cisla = [1.12, 4.51, 2.64, 13.1, 0.1]
```

Vytvořte seznam, který obsahuje

- každé z čísel ze seznamu cisla vynásobené dvěma,
- každé z čísel ze seznamu cisla s opačným znaménkem,
- každé z čísel ze seznamu cisla umocněné na druhou,
- každé z čísel ze seznamu cisla jako řetězec.

<details>
<summary><b>Řešení</b></summary>


```python
krat_dva = [n * 2 for n in cisla]
minus = [-n for n in cisla]
na_druhou = [n ** 2 for n in cisla]
jako_str = [str(n) for n in cisla]
```

</details>
