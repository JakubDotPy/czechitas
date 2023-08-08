## Půjčovna ◇◆◆◆◆

Půjčovna aut má v každém kraji ČR jedno auto s danou SPZ. Ke konci roku chce zjistit, kolik všechna auta najezdila dohromady kilometrů. V souboru auta.txt je pro každou SPZ zaznamenáno kolik dané auto ujelo kilometrů za daný rok. Hodnoty jsou v tisících kilometrů. Bohužel se v jednotlivých krajích blbě zkoordinovali a někdo používal desetinnou čárku, někdo zase tečku.

**Pozor!** V souboru s daty je ještě jeden problém, který není na první pohled vidět!

Napište program, který na výstup vypíše součet všech ujetých kilometrů. Jistě se vám bude hodit metoda řetězců jménem `replace()`.

### Řešení

```python
ujete_kilometry = 0
with open(r'auta.txt', encoding='utf-8') as file:
    for radek in file:
        kilometry = float(radek.replace(',', '.').split(' ')[-1])
        ujete_kilometry += kilometry

print(f'celkovy pocet ujetych kilometru je {ujete_kilometry}')
```