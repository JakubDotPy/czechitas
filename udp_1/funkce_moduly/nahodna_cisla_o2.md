## Náhodná čísla ◇◇◇◆◆

Na informačním panelu v předsálí divadla se zobrazují informace o náhodných představeních. Pro tento panel potřebujeme
generátor náhodných čísel, který bude generovat čísla představení mezi 1 až 24. Importujte modul `random` a použijte
funkci `randint()` pro vygenerování několika náhodných čísel z tohoto rozsahu.

### Řešení

```python
import random

cislo = random.randint(1, 24)
```