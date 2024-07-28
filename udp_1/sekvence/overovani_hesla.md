## Ověřování hesla

Ověřování hesla se někdy dělá tak, že se vás systém ptá pouze na některé jeho znaky. Napište program, který má uloženo
heslo, které musí uživatel zadat. Pak se jej postupně zeptejte například na druhý, pátý a sedmý znak hesla. Propusťte
uživatele pouze tehdy, zadá-li všechny tyto znaky správně.

<details>
<summary><b>Řešení</b></summary>

```python
heslo = 'tajneHeslo345@'

znak_2 = input('Zadej 2. znak hesla: ')
overeni_druheho = znak_2 == heslo[1]  # v promenne 'overeni_druheho' bude bud False, nebo True

znak_5 = input('Zadej 5. znak hesla: ')
overeni_pateho = znak_5 == heslo[4]

znak_7 = input('Zadej 7. znak hesla: ')
overeni_sedmeho = znak_7 == heslo[6]

if overeni_druheho and overeni_pateho and overeni_sedmeho:  # pokud jsou vsechny tri overeni True
    print('Ověření bylo úspěšné!')
else:
    print('Ověření neúspěšné!')
```

</details>
