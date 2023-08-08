## Prvočíslo ◇◆◆◆◆

Požádej uživatele o zadání celého čísla. Následně urči, zda je toto číslo prvočíslo.

Prvočíslo je číslo, které je dělitelné beze zbytku pouze 2 čísly - 1 a sebou samotným.

- Například 5 je prvočíslo, protože je dělitelná pouze 1 a 5.
- Naopak 4 není prvočíslo, protože je dělitelná 1, 2 a 4.

### Řešení

*pozn.: Níže je velmi neefektivní způsob. Samozřejmě existují specializované algorytmy.*

```python
testovane = int(input('Zadej číslo na otestování: '))

prvocislo = True
for n in range(2, testovane):
    if testovane % n == 0:
        prvocislo = False
        break

print(f'cislo {testovane} {"je" if prvocislo else "není"} prvocislo')
```