## Střed seznamu podruhé

Sestavte vzoreček, který vrátí číslo nacházející se přesně uprostřed v zadaném seznamu s.
Tentokrát však u seznamů sudé délky vyberte jako střed číslo blíž k začátku seznamu.

<details>
<summary><b>Řešení</b></summary>

```python
s = [1, 2, 3, 5, 8, 15, 56]

if len(s) % 2 == 0:  # je sudy
    index = len(s) // 2 - 1
else:
    index = len(s) // 2

stred = s[index]

print(f'stred {s} je {stred}')
```

</details>
