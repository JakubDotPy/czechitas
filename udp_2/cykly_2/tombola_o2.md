## Tombola ◇◇◇◆◆

V tombole bylo prodáno celkem 1000 lístků. Naším úkolem je vylosovat náhodně tři výherce. Napište program, který
vygeneruje a vypíše tři čísla mezi 1 a 1000.  
Využijte funkci `randint`, nezapomeňte ale, že si ji musíte importovat z modulu `random`.

Neřešte, že jedno číslo může být vygenerováno dvakrát.

<details>
<summary><b>Řešení</b></summary>


```python
import random

for _ in range(3):
    print(random.randint(1, 1000))
```

</details>
