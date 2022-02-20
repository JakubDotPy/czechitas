# Cvičení

## 1 - Vysvědčení ○○○♦♦

Uvažujme vysvědčení, které máme zapsané jako slovník.

```python
vysvedceni = {
    "Český jazyk"     : 1,
    "Anglický jazyk"  : 1,
    "Matematika"      : 1,
    "Přírodopis"      : 2,
    "Dějepis"         : 1,
    "Fyzika"          : 2,
    "Hudební výchova" : 4,
    "Výtvarná výchova": 2,
    "Tělesná výchova" : 3,
    "Chemie"          : 4,
    }
```

- Napiš program, který spočte průměrnou známku ze všech předmětů.
- Uprav program, aby vypsal všechny předměty, ve kterých získal student známku 1.

### Řešení

```python
vysvedceni = {
    "Český jazyk"     : 1,
    "Anglický jazyk"  : 1,
    "Matematika"      : 1,
    "Přírodopis"      : 2,
    "Dějepis"         : 1,
    "Fyzika"          : 2,
    "Hudební výchova" : 4,
    "Výtvarná výchova": 2,
    "Tělesná výchova" : 3,
    "Chemie"          : 4,
    }

prumerna_znamka = sum(vysvedceni.values()) / len(vysvedceni)
print(f'Průměrná známka je: {prumerna_znamka}')

print('Předměty s jedničkou:')
for predmet, znamka in vysvedceni.items():
    if znamka == 1:
        print('\t' + predmet)
```

## 2 - Čtenářský deník ○○○♦♦

Gustav je vášnivým čtenářem detektivek z našeho nakladatelství a navíc si zapisuje knihy, které přečetl.  
Níže ve slovníku vidíme, jaké informace si eviduje - název knihy, počet stran a hodnocení od 0 do 10.

```python
knihy = [
    {'nazev': 'Vražda s příliš mnoha notami', 'pocet_stran': 450, 'hodnoceni': 5},
    {'nazev': 'Vražda podle knihy', 'pocet_stran': 524, 'hodnoceni': 9},
    {'nazev': 'Past', 'pocet_stran': 390, 'hodnoceni': 4},
    {'nazev': 'Popel popelu', 'pocet_stran': 411, 'hodnoceni': 10},
    {'nazev': 'Noc, která mě zabila', 'pocet_stran': 159, 'hodnoceni': 7},
    {'nazev': 'Vražda, kouř a stíny', 'pocet_stran': 258, 'hodnoceni': 6},
    {'nazev': 'Zločinný steh', 'pocet_stran': 542, 'hodnoceni': 8},
    {'nazev': 'Zkus mě chytit', 'pocet_stran': 247, 'hodnoceni': 7},
    {'nazev': 'Vrah zavolá v deset', 'pocet_stran': 396, 'hodnoceni': 6},
    ]
```

- Napiš program, který spočte celkový počet stran, které Gustav přečetl.
- Připiš do programu výpočet počtu knih, kterým dal Gustav hodnocení alespoň 8.

### Řešení

```python
knihy = [
    {'nazev': 'Vražda s příliš mnoha notami', 'pocet_stran': 450, 'hodnoceni': 5},
    {'nazev': 'Vražda podle knihy', 'pocet_stran': 524, 'hodnoceni': 9},
    {'nazev': 'Past', 'pocet_stran': 390, 'hodnoceni': 4},
    {'nazev': 'Popel popelu', 'pocet_stran': 411, 'hodnoceni': 10},
    {'nazev': 'Noc, která mě zabila', 'pocet_stran': 159, 'hodnoceni': 7},
    {'nazev': 'Vražda, kouř a stíny', 'pocet_stran': 258, 'hodnoceni': 6},
    {'nazev': 'Zločinný steh', 'pocet_stran': 542, 'hodnoceni': 8},
    {'nazev': 'Zkus mě chytit', 'pocet_stran': 247, 'hodnoceni': 7},
    {'nazev': 'Vrah zavolá v deset', 'pocet_stran': 396, 'hodnoceni': 6},
    ]

pocet_stran = 0
for kniha in knihy:
    pocet_stran += kniha['pocet_stran']

# NOTE: nebo lépe
# pocet_stran = sum(kniha['pocet_stran'] for kniha in knihy)

print(f'Přečetl {pocet_stran} stran.')

pocet_nad_osm = 0
for kniha in knihy:
    if kniha['hodnoceni'] >= 8:
        pocet_nad_osm += 1
print(f'Počet knih s hodnocením >= 8: {pocet_nad_osm}')
```

# Bonusy

## 3 - Poznávací značky ○○♦♦♦

V následujícím slovníků je evidence automobilů. Klíčem jsou státní poznávací značky (SPZ) a hodnotou je jméno majitele
vozu.

```python
spzetky = {
    "4A2 3000": "František Novák",
    "6P5 4747": "Jana Pilná",
    "3B7 3652": "Jaroslav Sečkár",
    "1P5 5269": "Marta Nováková",
    "37E 1252": "Martina Matušková",
    "2A5 2241": "Jan Král"
    }
```

- Napiš program, který vypíše všechny majitele, jejichž vozidlo je registrováno v Plzeňském kraji, tj. na druhém místě (
  index 1) řetězce v klíči je písmeno P.

```python
spzetky = {
    "4A2 3000": "František Novák",
    "6P5 4747": "Jana Pilná",
    "3B7 3652": "Jaroslav Sečkár",
    "1P5 5269": "Marta Nováková",
    "37E 1252": "Martina Matušková",
    "2A5 2241": "Jan Král"
    }
print('Lidé z Plzeňského kraje:')
for spz, jmeno in spzetky.items():
    if spz[1] == 'P':
        print(f'- {jmeno}')
```