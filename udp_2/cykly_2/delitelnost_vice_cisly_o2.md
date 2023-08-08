## Dělitelnost více čísly ◇◇◇◆◆

Vypišme si čísla z nějakého rozsahu na základě jejich dělitelnosti dvěma čísly.

- Zkuste z nějakého rozsahu čísel vypsat čísla, která jsou dělitelná 3 i 4 současně.
- Zkuste z nějakého rozsahu čísel vypsat čísla, která jsou dělitelná 5 nebo 6.  
  Stačí vypsat text: `"Číslo je dělitelné 5 nebo 6."`

### Řešení

```python
for n in range(30):
    delitelne_3 = n % 3 == 0
    delitelne_4 = n % 4 == 0
    if delitelne_3 and delitelne_4:
        print(f'{n} je dělitelné 3 i 4')

    delitelne_5 = n % 5 == 0
    delitelne_6 = n % 6 == 0
    if delitelne_5 or delitelne_6:
        print(f'{n} je dělitelné 5 nebo 6')
```