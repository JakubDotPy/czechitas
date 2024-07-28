## Házení kostkou

- Napište program, který při každém spuštění hodí šestistěnnou kostkou ‒ tedy vypíše náhodné číslo mezi 1 až 6.
- Upravte program tak, aby jako parametr dostal počet stěn kostky. Bude tedy umět házet třeba sedmistěnnou nebo devítistěnnou kostkou podle toho, jaké číslo dostane na vstupu.
- Předejte programu další parametr, který bude udávat kolik hodů má program provést. Program pak na výstup vytiskne seznam tolika hodů, kolik jste zadali na vstupu. Cílem je tedy vymyslet, jak vyrobit seznam náhodných čísel.

<details>
<summary><b>Řešení</b></summary>


Ukážeme si rovnou třetí bod 

```python
import sys
import random

pocet_sten = int(sys.argv[1])
pocet_hodu = int(sys.argv[2])

hody = [random.randint(1, pocet_sten) for _ in range(pocet_hodu)]

print(hody)
```


</details>
