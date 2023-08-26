## Rodná čísla ◇◇◆◆◆

V následujícím seznamu máš seznam rodných čísel pacientů, kteří navštívili v jeden konkrétní den lékařskou ordinaci.

```python
rodna_cisla = [
    '845128/6219',
    '801002/5021',
    '900116/8291',
    '790501/7894',
    '850706/9259',
    '891222/1824',
    '870327/9582',
    '810602/6883',
    '850512/5070',
    '790531/7081'
]
```

- Kolik přišlo mužů a kolik žen?
- Kdy se narodil nejstarší a kdy nejmladší pacient?


Pokud nevíš, jak funguje rodné číslo, vysvětlení je níže:  
Rodné číslo je identifikační číslo, které slouží k jednoznačné identifikaci osoby. V České republice se rodné číslo
skládá z 10 číslic a jednoho lomítka, které ho rozděluje na části.
- Prvních 6 číslic udává datum narození v pořadí rok (2 číslice), měsíc (2 číslice) a den (2 číslice). Například pro
narození 2. února 1990 by prvních 6 číslic mělo být 900202. Zbytek rodného čísla (tj. část za lomítkem) slouží k
identifikaci konkrétní osoby.
- Ženy mají k číslu měsíce přičteno 50, např. 845128/6219 je číslo patřící ženě.*

<details>
<summary><b>Řešení</b></summary>


```python
pocet_muzu = 0
datumy_jako_cislo = []

for rodne_cislo in rodna_cisla:
    ciselne_datum = int(rodne_cislo[:6])
    if int(rodne_cislo[2]) >= 5:  # zena
        ciselne_datum -= 5_000
    else:
        pocet_muzu += 1
    datumy_jako_cislo.append(ciselne_datum)

print(f'přišlo {pocet_muzu} mužů a {len(rodna_cisla) - pocet_muzu} žen')

print(f'nejmladsi se narodil {max(datumy_jako_cislo)}')
print(f'nejstarší se narodil {min(datumy_jako_cislo)}')
```


</details>
