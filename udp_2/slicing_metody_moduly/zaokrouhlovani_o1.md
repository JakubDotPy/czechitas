## Zaokrouhlování ◇◇◇◇◆

Napište program, který dostane na vstupu desetinné číslo a na výstup napíše toto číslo zaokrouhlené nejdříve nahoru,
potom dolů a potom běžným Pythonovským zaokrouhlováním.

### Řešení

```python
import math

num = float(input('zadej cislo: '))

print(f'nahoru: {math.ceil(num)}')
print(f'dolu:  {math.floor(num)}')
print(f'round: {round(num)}')
```