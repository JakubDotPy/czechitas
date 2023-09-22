## Střed seznamu ◇◆◆◆◆

Sestavte výraz, který vrátí číslo nacházející se přesně uprostřed v zadaném seznamu `s`.
U seznamů liché délky je střed jasně definovaný, ovšem u seznamů sudé délky nám padne mezi dvě čísla. V takovém případě
vyberte jako střed číslo blíže ke konci seznamu.

<details>
<summary><b>Řešení</b></summary>


```python
s = [1, 2, 3, 5, 8, 15, 56]

stred = s[len(s) // 2]

print(f'stred {s} je {stred}')
```

</details>
