## Zarovnání výpisu ◇◆◆◆◆

Vypište seznam čísel každé na nový řádek zarovnané vpravo na délku nejdelšího čísla.

```python
numbers = [7728, 88, 958621, 5941, 959847272, 3944, 80, 521, 57035, 3967894]
```

Návod: Zjistěte kolik znaků zabírá nejdelší číslo ze seznamu
Napište funkci, která dostane řetězec a délku, na kterou má text vyplnit zleva mezerami

Bonus: funkce bude mít volitelný parametr, jakým znakem má text vyplňovat

Výstup:

```text
     7728
       88
   958621
     5941
959847272
     3944
       80
      521
    57035
  3967894
```

Výstup bonusu:

```text
.....7728
.......88
...958621
.....5941
959847272
.....3944
.......80
......521
....57035
..3967894
```

### Řešení

```python
def zarovnej(retezec, delka, znak=' '):
    zleva = delka - len(retezec)
    print(znak * zleva + retezec)


nejdelsi = 0
for n in numbers:
    aktualni_delka = len(str(n))
    if aktualni_delka > nejdelsi:
        nejdelsi = aktualni_delka

# ted uz jen pomoci funkce vypiseme
for n in numbers:
    zarovnej(str(n), nejdelsi)

# a jako bonus
for n in numbers:
    zarovnej(str(n), nejdelsi, '.')
```