# Cvičení

## 1 - Řetězce jako sekvence ○○○♦♦

- Uložte do proměnné `jmeno` svoje celé jméno a nechte vypsat jeho třetí, pátý a sedmý znak.  
  Vyzkoušejte, co se stane, když budete chtít znak na pozici, která překračuje délku řetězce.

### Řešení

```python
uzivatel = input('Zadej uživatelské jméno: ')
print(uzivatel[2])
print(uzivatel[4])
print(uzivatel[6])
print(uzivatel[60])
```

## 2 - Seznamy ○♦♦♦♦

- Vytvořte nějaký seznam celých čísel, například počty diváků na několika po sobě jdoucích představeních.
- Vytvořte nějaký seznam desetinných čísel, například zaplněnost divadla v několika po sobě jdoucích představeních.
- Vytvořte nějaký seznam řetězců, například seznam názvů několika divadelních představení, která divadlo hraje. Uložte
  tento seznam do proměnné `hry`. Uložte do nějaké proměnné druhou položku tohoto seznamu.
- Do proměnné `hodnoceni` uložte seznam hodnocení, které obdržela divadelní hra
  *Plyšáci na útěku* v různých recenzních časopisech. Hodnocení je vždy dvouprvkový seznam obsahující název recenzního
  časopisu jako řetězec a samotné hodnocení jako číslo mezi 1 až 10.

### Řešení

```python
pocty_divaku = [120, 100, 95, 78, 100]

zaplnenost = [0.9, 0.8, 0.7, 0.65, 0.8, 0.85]

hry = ['Hra A', 'Hra B', 'Hra C', 'Hra D', 'Hra E', 'Hra F']
druha_hra = hry[1]

hodnoceni = [
    ['Casopis A', 5],
    ['Casopis B', 8],
    ['Casopis C', 7],
]
```

# Bonusy

## 3 - Ověřování hesla ○○♦♦♦

Ověřování hesla se někdy dělá tak, že se vás systém ptá pouze na některé jeho znaky. Napište program, který má uloženo
heslo, které musí uživatel zadat. Pak se jej postupně zeptejte například na druhý, pátý a sedmý znak hesla. Propusťte
uživatele pouze tehdy, zadá-li všechny tyto znaky správně.

### Řešení

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