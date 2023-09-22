## Úprava řetězce ◇◇◇◆◆

Napište program, který dostane jako jeden parametr řetězec s mezerami (aby to fungovalo, musí být ten řetězec obalen v
uvozovkách). Vypište tento řetězec tak, že mezery nahradíte za podtržítka.

```text
python uprava_retezce.py "retezec s mezerami"
retezec_s_mezerami
```

<details>
<summary><b>Řešení</b></summary>


```python
import sys

retezec = sys.argv[1]
print(retezec.replace(' ', '_'))
```

</details>
