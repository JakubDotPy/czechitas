## Jednoduché podmínky ◇◇◇◆◆

- Založte si program `prihlaseni.py`. V tomto nechte uživatele zadat svoje uživatelské jméno a poté heslo.
  Pokud se heslo neshoduje s heslem `'simsalabim'`, vypište na výstup `Vstup nepovolen` a zavolejte funkci `exit()`,
  aby uživatel neznalý hesla nemohl s programem dál pracovat.

- Na konec programu vlož příkaz, který se uživatele zeptá na věk. Pokud je uživatel starší 18 let, vypište na výstup
  `Smíš vstoupit` Pokud je mladší, vypiš `Vstup povolen od 18 let`.

<details>
<summary><b>Řešení</b></summary>


```python
# prihlaseni.py

uzivatel = input('Zadej uživatelské jméno: ')
heslo = input('Zadej heslo: ')

if heslo != 'simsalabim':
    print('Vstup nepovolen!')
    exit()

vek = int(input('Zadej věk: '))
if vek >= 18:
    print('Smíš vstoupit.')
else:
    print('Vstup nepovolen!')
```

</details>
