## Registrace ◇◇◇◆◆

Založte si program `registrace.py`. Program nechá uživatele, aby si zvolil uživatelské jméno a heslo. Heslo jej nechejte
zadat dvakrát a ověřte, že jej uživatel zadal dvakrát stejně. V opačném případě vypište varování, že hesla nejsou
stejná. Při prvním zadávání ověřte, že heslo je bezpečné, což v tomto případě znamená, že je delší než 8 znaků.

<details>
<summary><b>Řešení</b></summary>


```python
# registrace.py
uzivatel = input('Zadej uživatelské jméno: ')

heslo = input('Zadej heslo: ')
if len(heslo) <= 8:
    print('Heslo je příliš krátké')
    exit()

heslo_2 = input('Zadej heslo znovu: ')
if heslo != heslo_2:
  print('Hesla se neshodují.')
```


</details>
