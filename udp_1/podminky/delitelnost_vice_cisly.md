## Dělitelnost více čísly

Požádejme uživatele, ať zadá celé číslo. Napiš program který zjistí, zda je číslo dělitelné 3 i 4 současně.

Tip: nezapomeňte si zadané číslo převést na int. Tip 2: K ověření dědičnosti použij operátor % - zbytek po celočíselném
dělení a zkontroluj, zda je výsledek 0. Například 15 % 5 vrací 0, protože 15 je dělitelné 5.

<details>
<summary><b>Řešení</b></summary>

```python
cislo = int(input('Zadej celé číslo: '))

delitelne_3 = cislo % 3 == 0
delitelne_4 = cislo % 4 == 0

if delitelne_3 and delitelne_4:
  print('je delitelne 3 i 4')
else:
  print('neni delitelne 3 i 4 soucasne')
```

</details>
