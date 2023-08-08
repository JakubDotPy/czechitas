## Pohyby na účtu ◇◇◇◆◆

Mějme seznam pohybů na nějakém bankovním účtu:

```python
pohyby = [1200, -250, -800, 540, 721, -613, -222]
```

- Vypište v pořadí třetí pohyb z uvedeného seznamu.
- Vypište všechny pohyby kromě prvních dvou.
- Vypište kolik je všech pohybů dohromady.
- Pomocí volání vhodných funkcí vypište nejvyšší a nejnižší pohyb.
- Spočítejte celkový přírůstek na účtu za dané období. Pozor, že přírůstek může vyjít i záporný.

### Řešení

```python
pohyby = [1200, -250, -800, 540, 721, -613, -222]

# v poradi treti
print(pohyby[2])

# vsechny krome dvou prvnich
print(pohyby[2:])

# vsechny dohromady
print(len(pohyby))

# nejvyssi a nejnizsi
print(f'nejnizsi je {min(pohyby)}, nejvyssi {max(pohyby)}')

# celkovy prirustek
print(f'zustatek = {sum(pohyby)}')
```