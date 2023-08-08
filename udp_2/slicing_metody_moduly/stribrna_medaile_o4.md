## Stříbrná medaile ◇◆◆◆◆

Stříbrná medaile je sice úžasný úspěch, ale kdo by nechtěl vyhrát? Podívejme se, kolik chybělo stříbrnému běžci k
vítězství.

- Nejprve si vytvoř dvě proměnné, do kterých ulož čas vítěze a čas závodníka se stříbrnou medailí. Oba časy převeď na
  minuty a ulož jako číslo.
- Vypočti rozdíl obou proměnných. Tím zjistíš, kolik minut chybělo stříbrnému závodníku k vítězství.

### Řešení

```python
vysledky = [
    ["Brunner Radek", [3, 0, 9]],
    ["Urban Jaroslav", [3, 11, 44]],
    ["Andrle Jakub", [3, 12, 21]],
    ["Fiala Stanislav", [3, 13, 31]]
]

#                  hodiny                   minuty               vteriny
vitezny_cas = vysledky[0][1][0] * 60 + vysledky[0][1][1] + vysledky[0][1][2] / 60
stribrny_cas = vysledky[1][1][0] * 60 + vysledky[1][1][1] + vysledky[1][1][2] / 60

rozdil = stribrny_cas - vitezny_cas
```