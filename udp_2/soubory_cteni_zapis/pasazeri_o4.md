## Pasažéři

Autobus mezi Zdebudevsí a Kozoprdy jezdí čtyřikrát denně každý všední den v týdnu. Za poslední týden jsme naměřili počty pasažérů pro každou jízdu tam i zpět. Data jsou uložená v souboru pasazeri.txt. Jízda vždy obsahuje dvě čísla oddělená čárkou, která udávají počet pasažérů směrem tam a směrem zpět.

- Napište program, který pro první den vypíše, kolik pasažérů jelo celkem směrem tam a kolik směrem zpět.
- Nechť váš program vypisuje součty pasažérů ze celý týden, tedy kolik lidí za celý týden jelo směrem tam a kolik směrem zpět.

<details>
<summary><b>Řešení</b></summary>


```python
cesty = {}

with open('pasazeri.txt', encoding='utf-8') as vstup:
    cislo_dne = 0
    for radek in vstup:
        den = {
            'tam' : [],
            'zpet': [],
        }
        for tam_zpatky in radek.split():
            tam_zpatky = tam_zpatky.split(',')
            den['tam'].append(int(tam_zpatky[0]))
            den['zpet'].append(int(tam_zpatky[1]))
        cesty[cislo_dne] = den
        cislo_dne += 1

print(f'prvni den tam: {sum(cesty[0]["tam"])}')
print(f'prvni den zpet: {sum(cesty[0]["zpet"])}')

celkem_tam = 0
celkem_zpet = 0
for den, data in cesty.items():
    celkem_tam += sum(data['tam'])
    celkem_zpet += sum(data['zpet'])

print(f'celkem jelo {celkem_tam} lidi tam a {celkem_zpet} lidi zpet')
```

</details>
