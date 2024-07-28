## Hádání čísla

Napište interaktivní hru, ve které počítač vygeneruje tajné číslo v rozsahu 1 až 100 (použijte
funkci `random.randint()`).  
Následně se v cyklu ptejte uživatele, aby zadal číslo a vypisujte vždy jestli je zadané číslo nižší nebo vyšší než tajné
číslo. Ukončete cyklus v momentě, kdy uživatel trefí tajné číslo.

<details>
<summary><b>Řešení</b></summary>


```python
import random

hadane_cislo = random.randint(1, 100)

while True:
    tip = int(input('hádej: '))

    if tip == hadane_cislo:
        print('Uhodl jsi!')
        break

    if tip > hadane_cislo:
        print('hadane cislo je nižší')
    elif tip < hadane_cislo:
        print('hádané číslo je vyšší')
```

</details>
