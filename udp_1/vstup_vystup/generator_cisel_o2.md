## Generátor čísel ◇◇◇◆◆

Napište program `generator.py`, který si od uživatele vyžádá dvě celá čísla - dolní mez a horní mez - a vypíše na výstup
náhodné číslo v zadaných mezích.

### Řešení

```python
# generator.py

import random

dolni_mez = int(input('Zadej dolní mez: '))
horni_mez = int(input('Zadej horní mez: '))
cislo = random.randint(dolni_mez, horni_mez)
print(cislo)
```