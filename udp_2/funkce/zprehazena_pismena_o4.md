## Zpřeházená písmena ◇◆◆◆◆

Slovo je stále možné pohodlně přečíst, když jsou pomíchaná písmena. Stačí, když první a poslední písmeno je na své
pozici zachováno. Napiš funkci, která bude mít jako vstupní parametr slovo a vrátí slovo, kde zpřehází všechny znaky
kromě prvního a posledního.

Nápověda: `random.shuffle()`

Super bonus: Napiš program, který takovou funkci využije na delší text více slov.

### Řešení

```python
import random


def zamichej_slovo(slovo):
    pismena_jako_list = list(slovo)
    stred = pismena_jako_list[1:-1]
    random.shuffle(stred)
    return slovo[0] + ''.join(stred) + slovo[-1]


print(zamichej_slovo('lokomotiva'))

text = '''Slovo je stále možné pohodlně přečíst, když jsou pomíchaná písmena.
Stačí, když první a poslední písmeno je na své pozici zachováno. Napiš funkci,
která bude mít jako vstupní parametr slovo a vrátí slovo, kde zpřehází všechny
znaky kromě prvního a posledního.
'''

zamichana_slova = []
for slovo in text.split():
    zamichana_slova.append(zamichej_slovo(slovo))

vysledny_text = ' '.join(zamichana_slova)
print(vysledny_text)
```