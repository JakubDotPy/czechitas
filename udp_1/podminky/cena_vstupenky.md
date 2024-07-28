## Cena vstupenky

A nyní opět pokračujeme v našem rezervačním systému.

- Program `vstupenky_01.py`, který jste napsali v předchozí fázi, si uložte jako `vstupenky_02.py`, abychom ho mohli
  dále rozšířit o výpočet ceny vstupenky.
- Jakmile máte v programu načtený věk uživatele, vytvořte si proměnnou `plna_cena`, do které uložte hodnotu 12.
- Vytvořte podmínku, která do proměnné `cena` uloží cenu spočítanou podle věku uživatele dle následujících pravidel
    - 0 euro pro návštěvníky mladší 6 let
    - 65% ze základní ceny pro návštěvníky 6 až 26 let (žák, student)
    - 100% ze základní ceny pro návštěvníky 27 až 64 let (dospělý)
    - 50% ze základní ceny pro ostatní (senior).

Nezapomeňte na zaokrouhlování, ať nám cena vyjde v celých centech.

- Nakonec spočtenou cenu vypište s nějakou hezkou zprávou na výstup.

<details>
<summary><b>Řešení</b></summary>

```python
# vstupenka_02.py

print('Divadlo Pěst na oko')
print('Vítejte v online rezervaci vstupenek')
print('Pro vstup do systému je potřeba registrace')

uzivatel = input('Zadej uživatelské jméno: ')
vek = int(input('Zadej věk: '))

plna_cena = 12
if vek < 6:
    cena = 0
elif vek <= 26:
    cena = plna_cena * 0.65
elif vek <= 64:
    cena = plna_cena
else:
    cena = plna_cena * 0.5

print(f'Cena vstupenky je {round(cena, 2)}.')
```

</details>
