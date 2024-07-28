## Čas v minutách

Napište program `minuty.py`, která dělá obrácenou věc než program `cas.py` z textu výše. Když mu na příkazové řádce
předáme dva parametry ‒ počet hodin a počet minut ‒ například takto

```text
python minuty.py 2 54
```

program nám vrátí délku tohoto času minutách. V tomto případě tedy číslo 174.

- Nejprve program napište tak, že si hodnoty 2 a 54 uložíte přímo natvrdo v programu do nějakých proměnných a z nich
  spočítáte a vytisknete výsledek.
- Až když váš program bude fungovat, zkuste tyto proměnné načíst z parametrů příkazové řádky. Nezapomeňte, že parametry
  jsou vždy řetězce a že první parametr je vždy název vašeho programu.

<details>
<summary><b>Řešení</b></summary>


ukážeme si rovnou druhou variantu

```python
import sys

hodiny = int(sys.argv[1])
minuty = int(sys.argv[2])

print(hodiny * 60 + minuty)
```

</details>
