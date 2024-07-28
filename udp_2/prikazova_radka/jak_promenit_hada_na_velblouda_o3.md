## Jak proměnit hada na velblouda

Napište program, který dostane na příkazovém řádku název proměnné v hadí notaci a vrátí tentýž název zapsaný ve velbloudí notaci.

Příklad:

```text
python had-velbloud.py had_honi_velblouda
hadHoniVelblouda
```

<details>
<summary><b>Řešení</b></summary>


```python
import sys

retezec = sys.argv[1]

title_s_mezerami = retezec.replace('_', ' ').title()
prvni_male = title_s_mezerami[0].lower() + title_s_mezerami[1:]
vysledek = ''.join(prvni_male.split())

print(vysledek)
```


</details>
