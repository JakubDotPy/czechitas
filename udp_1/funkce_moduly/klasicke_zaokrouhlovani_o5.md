## Klasické zaokrouhlování[^1] ◆◆◆◆◆

Překvapivě Python neobsahuje[^2] žádnou funkci, která by dělala klasické zaokrouhlování, tedy takové, na které jsme
všichni zvyklí ze školy. S něčím takovým se nemůžeme spokojit.

- Zkuste vymyslet (za použití funkcí, které už znáte) příkaz, který zaokrouhlí číslo v proměnné `cislo` na celé číslo
  klasickým zaokrouhlováním.

- Pokud si chcete svoje řešení otestovat, můžete si obsah proměnné `cislo` vygenerovat náhodně funkcí `random.uniform()`
  . Ta má stejné vstupy jako funkce `random.randint()`, generuje ale desetinná čísla.

[^1]: Tento příklad se dá považovat za zajímavost, protože klasické zaokrouhlování `round` zaokrouhluje hraniční případy
2.5, 3.5, ... vždy k *nejbližšímu sudému celému číslu*.  
[^2]: Python tuto funkci samozřejmě obsahuje. Hned několik zaokrouhlovacích funkcí najdete v
modulu [`decimal`](https://docs.python.org/3/library/decimal.html#rounding-modes)

<details>
<summary><b>Řešení</b></summary>


```python
import math
import random

cislo = 2.5
zaokrouhlene = math.floor(cislo + 0.5)

cislo = random.uniform(0, 10)
zaokrouhlene = math.floor(cislo + 0.5)
```

</details>
