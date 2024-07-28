## Zakázka pro divadlo

Divadlo požaduje systém pro online rezervaci vstupenek na pořádaná představení. Váš první úkol na této zakázce je
vytvořit registraci pro nové uživatele tohoto systému.

- Založte si program `vstupenky_01.py`. Bude to první verze našeho programu pro nákup vstupenek.
- Napište program tak, aby nejprve vypsal na obrazovku *Divadlo Pěst na oko* na první řádek, na druhý řádek chceme
  vypsat *Vítejte v online rezervaci vstupenek* a na třetí řádek *Pro vstup do systému je potřeba registrace*.
- Na dalším řádku požádejte uživatele o jeho uživatelské jméno a poté o jeho věk. Ten si uložte to nějaké proměnné jako
  číslo.

<details>
<summary><b>Řešení</b></summary>


```python
# vstupenky_01.py

print('Divadlo Pěst na oko')
print('Vítejte v online rezervaci vstupenek')
print('Pro vstup do systému je potřeba registrace')
uzivatel = input('Zadej uživatelské jméno: ')
vek = int(input('Zadej věk: '))
```

</details>
