## Jednoduchý vstup

Teď už budeme chtít, aby náš program dokázal získat vstup od uživatele.

- Napište program `jmeno.py`, který získá jméno a příjmení od uživatele voláním funkce `input()`. Vypište je na
  obrazovku podobně jako v předchozím cvičení.
- Nechte uživatele zadat také věk. Pozor na to, že funkce `input()` vždy vrací řetězec, ale my chceme v proměnné vek mít
  číslo. Použijte tedy funkci `int()`, abyste převedli uživatelem zadaný řetězec na číslo. Opět vypište na obrazovku
  jméno, příjmení a věk tak jako v předchozí verzi.

<details>
<summary><b>Řešení</b></summary>

```python
# jmeno.py

jmeno = input('Zadej jméno: ')
prijmeni = input('Zadej příjmení: ')
print(f'{jmeno} {prijmeni}')

vek = input('Zadej věk: ')
vek = int(vek)
print(f'{jmeno} {prijmeni}, věk: {vek}')
```

</details>
