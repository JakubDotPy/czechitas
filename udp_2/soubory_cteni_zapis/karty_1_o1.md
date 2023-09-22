## Karty 1 ◇◇◇◇◆

Napište program, který vylosuje náhodnou hrací kartu z klasické whistové sady obsahující 52 karet, rozdělených do čtyř barev (kříže, srdce, piky, káry), s hodnotami 2, 3, 4, 5, 6, 7, 8, 9, 10, J (kluk), Q (dáma), K (král), A (eso).

Výstup programu může vypadat například takto:

```text
Karta: kluk kříže
```

<details>
<summary><b>Řešení</b></summary>


```python
import random

hodnoty = list(range(2, 11)) + ['J', 'Q', 'K', 'A']
barvy = ['kříže', 'srdce', 'piky', 'káry']

print(f'Karta: {random.choice(hodnoty)} {random.choice(barvy)}')
```

</details>
