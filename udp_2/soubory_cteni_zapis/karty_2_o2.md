## Karty 2 ◇◇◇◆◆

Napište program, který vylosuje seznam 4 náhodných hracích karet podobně jako v předchozím úkolu. Můžeme si představovat, že rozdáváme karty například v pokeru. Zatím pro jednoduchost nebudeme řešit, že se nám může nějaká karta v seznamu opakovat.

- Vymyslete, jak budete vylosovanou kartu v seznamu reprezentovat. Vypište pak tento seznam na výstup.
- Dále k tomuto seznamu vypište součet hodnot všech vylosovaných karet. Položme hodnotu karet J, Q a K rovnu deseti a eso rovnu jedné.

<details>
<summary><b>Řešení</b></summary>


```python
import random

hodnoty = list(range(2, 11)) + ['J', 'Q', 'K', 'A']
body = list(range(2, 11)) + [10, 10, 10, 1]
barvy = ['kříže', 'srdce', 'piky', 'káry']

karty = []
for index in range(13):  # cislo karty
    for barva in barvy:
        # kartu nam reprezejntuje trojice (body, hodnota, barva)
        # napr.: (10, 'J', 'srdce')
        karta = (body[index], hodnoty[index], barva)
        karty.append(karta)

ruka = random.sample(karty, 4)
print(f'vylosovano {ruka}')

body = 0
for karta in ruka:
    body += karta[0]
    
print(f'mame celkem {body}')
```

</details>
