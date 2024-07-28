## Rámeček

Napiš funkci, která jako parametr převezme řetězec a vytiskne jej obalen hvězdičkami.

```text
Zadej slovo: ahoj
********
* ahoj *
********
```

<details>
<summary><b>Řešení</b></summary>

```python
def ramecek(slovo):
    delka = len(slovo)
    sirka_ramecku = delka + 4  # chceme trochu mista kolem slova
    print('*' * sirka_ramecku)
    print(f'* {slovo} *')
    print('*' * sirka_ramecku)


s = input('Zadej slovo: ')
ramecek(s)
```

</details>
