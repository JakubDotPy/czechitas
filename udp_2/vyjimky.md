# Cvičení: Výjimky

## 1 - Ošetření dělení nulou ◇◇◇◆◆

Předchozí ukázku uprav následujícím způsobem:

- Program bude na příkazové řádce očekávat dva parametry
- Parametry mohou být celá nebo desetinná čísla
- Vypiš podíl těchto čísel
- Ošetři, aby program nezhavaroval při pokusu o dělení nulou

Všechny chyby řeš ošetřováním výjimek.

### Řešení

```python
import sys

try:
    prvni_cislo = float(sys.argv[1])
    druhe_cislo = float(sys.argv[2])
    print(f'Zadány parametry: {prvni_cislo} a {druhe_cislo}')
    vysledek = prvni_cislo // druhe_cislo
    print(f'vysledek je {vysledek}')
except IndexError:
    print('Zadej dva parametry na příkazovou řádku!')
except ValueError:
    print('Zadej číslo jako parametr na příkazovou řádku!')
except ZeroDivisionError:
    print('Nesmíš dělit nulou.')
```
