# Cvičení

## 1 - Vysvědčení ○○○♦♦

Uvažujme vysvědčení, které máme zapsané jako slovník.

```python
school_report = {
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
school_report = {
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

prumerna_znamka = sum(school_report.values()) / len(school_report)
print(f'Průměrná známka je: {prumerna_znamka}')

print('Předměty s jedničkou:')
for predmet, znamka in school_report.items():
    if znamka == 1:
        print('\t' + predmet)
```

## 2 - Čtenářský deník ○○○♦♦

Gustav je vášnivým čtenářem detektivek z našeho nakladatelství a navíc si zapisuje knihy, které přečetl.  
Níže ve slovníku vidíme, jaké informace si eviduje - název knihy, počet stran a hodnocení od 0 do 10.

```python
books = [
    {"title": "Vražda s příliš mnoha notami", "pages": 450, "rating": 5},
    {"title": "Vražda podle knihy", "pages": 524, "rating": 9},
    {"title": "Past", "pages": 390, "rating": 4},
    {"title": "Popel popelu", "pages": 411, "rating": 10},
    {"title": "Noc, která mě zabila", "pages": 159, "rating": 7},
    {"title": "Vražda, kouř a stíny", "pages": 258, "rating": 6},
    {"title": "Zločinný steh", "pages": 542, "rating": 8},
    {"title": "Zkus mě chytit", "pages": 247, "rating": 7},
    {"title": "Vrah zavolá v deset", "pages": 396, "rating": 6},
    ]
```

- Napiš program, který spočte celkový počet stran, které Gustav přečetl.
- Připiš do programu výpočet počtu knih, kterým dal Gustav hodnocení alespoň 8.

### Řešení

```python
books = [
    {"title": "Vražda s příliš mnoha notami", "pages": 450, "rating": 5},
    {"title": "Vražda podle knihy", "pages": 524, "rating": 9},
    {"title": "Past", "pages": 390, "rating": 4},
    {"title": "Popel popelu", "pages": 411, "rating": 10},
    {"title": "Noc, která mě zabila", "pages": 159, "rating": 7},
    {"title": "Vražda, kouř a stíny", "pages": 258, "rating": 6},
    {"title": "Zločinný steh", "pages": 542, "rating": 8},
    {"title": "Zkus mě chytit", "pages": 247, "rating": 7},
    {"title": "Vrah zavolá v deset", "pages": 396, "rating": 6},
    ]

pocet_stran = 0
for book in books:
    pocet_stran += book['pages']

# NOTE: nebo lépe
# pocet_stran = sum(book['pages'] for book in books)

print(f'Přečetl {pocet_stran} stran.')

pocet_nad_osm = 0
for book in books:
    if book['rating'] >= 8:
        pocet_nad_osm += 1
print(f'Počet knih s hodnocením >= 8: {pocet_nad_osm}')
```

# Bonusy

## 3 - Poznávací značky ○○♦♦♦

V následujícím slovníků je evidence automobilů. Klíčem jsou státní poznávací značky (SPZ) a hodnotou je jméno majitele
vozu.

```python
plates = {
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
plates = {
    "4A2 3000": "František Novák",
    "6P5 4747": "Jana Pilná",
    "3B7 3652": "Jaroslav Sečkár",
    "1P5 5269": "Marta Nováková",
    "37E 1252": "Martina Matušková",
    "2A5 2241": "Jan Král"
    }
print('Lidé z Plzeňského kraje:')
for plate, name in plates.items():
    if plate[1] == 'P':
        print(f'- {name}')
```