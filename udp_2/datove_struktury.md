# Množiny

## 1 - Množiny ◇◇◆◆◆

Následující text převeďte na množinu unikátních znaků, zjistěte počet unikátních znaků a vypište jejich seřazený seznam.

```python
text = '''Prágl
Prágl, po anglánsku Prague nebo Praha nebo v Cajsku, je taková lochna
v tem kuse hródy někde za čárama naši domoviny, kde se zoncna už
nechláme a kde se prndá po cajzlovsku. A ještě k temu tam majó sicnu
těžcí papaláši, kvůli čemu ho má každé v láfu jako kaktus ve véfuku.
Z Práglu bere kramále aj ten jejich len kerému se péruje Vltava.

O Práglu se taky kóří, pač tam majó hafo retychů pro všecky. Kromě
bůry švédských retychů só aj dva v Olmecu a jeden v Bučovicách.
To my z našeho štatlu radši hážem lulec do kašny na Zelňáku. Když
ale nekdo vopruboval zašrajbčit náš barocké Parnas do cancu retychů
pro všecky, přišmrdolili se ti Švédi s tým, že só proti a hókajó po
celé hródě, že ta vasra v tem se dá chlemtat.
'''
```

Očekávaný výstup:

```text
49
['\n', ' ', ',', '.', 'A', 'B', 'C', 'K', 'O', 'P', 'T', 'V', 'Z', 'a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'r', 's', 't', 'u', 'v', 'y', 'z', 'á', 'é', 'í', 'ó', 'ý', 'č', 'ě', 'ň', 'ř', 'Š', 'š', 'ů', 'ž']
```

### Řešení

```python
unikatni = sorted(set(text))
print(len(unikatni))
print(unikatni)
```

*funkce `sorted` bere jako argument typ `iterable` (list, tuple, set...) a vrací seřazený list*

---

# Slovníky

## 1 - Vysvědčení ◇◇◇◇◆

Vytvoř slovník, který reprezentuje vysvědčení.  
Klíč slovníku bude název předmětu a hodnota známka z daného předmětu.  
Pro zjednodušení vlož do slovníku pouze tři předměty (například český jazyk, matematiku a dějepis).  
Vypiš obsah slovníku pomocí funkce `print()`.

### Řešení

```python
vysvedceni = {
    'matematika': 1,
    'cestina'   : 3,
    'dejepis'   : 2,
}
```

## 2 - Detektivky ◇◇◇◆◆

Vydavatel detektivek si eviduje prodané kusy u jednotlivých knih.  
V následujícím slovníku najdeš tři knihy a u každé z nich je počet prodaných kusů.

```python
prodano = {
    'Zkus mě chytit'     : 4165,
    'Vrah zavolá v deset': 5681,
    'Zločinný steh'      : 2565,
}
```

- Zkopíruj si slovník do svého programu.
- Přidej do slovníku nově vydanou detektivku `"Noc, která mě zabila"`, která zatím nebyla uvedena na trh, je tedy
  prodáno
  `0` kusů.
- U knihy `"Vrah zavolá v deset"` zvyš počet prodaných kusů o `100`.

### Řešení

```python
prodano['Noc, která mě zabila'] = 0

prodano['Vrah zavolá v deset'] += 100
```

## 3 - Tombola ◇◇◆◆◆

V následujícím slovníku jsou uložena čísla lístků tomboly a příslušné výhry.

```python
tombola = {
    7 : 'Láhev kvalitního vína Château Headache',
    15: 'Pytel brambor z místního družstva',
    23: 'Čokoládový dort',
    47: 'Kniha o historii města',
    55: 'Šiška salámu',
    67: 'Vyhlídkový let balónem',
    79: 'Moderní televizor',
    91: 'Roční předplatné městského zpravodaje',
    93: 'Společenská hra Sázky a dostihy',
}
```

- Napiš program, který se nejprve zeptá uživatele na číslo jeho lístku. Vstup uživatele si převeď na `int`!
- Zkontroluj, zda je číslo lístku ve slovníku. Pokud ne, vypiš text `"Bohužel nevyhráváš nic."` Pokud číslo ve slovníku
  je, vypiš uživateli, co vyhrál.
- Odeber výhru pro daný lístek ze slovníku, abychom tam evidovali pouze nevydané ceny.

### Řešení

```python
cislo_uzivatele = int(input('Zadej sve cislo listku: '))

if cislo_uzivatele in tombola:
    vyhra = tombola[cislo_uzivatele]
else:
    vyhra = 'Bohužel nevyhráváš nic.'

# NOTE: mnohem lepsi reseni
# vyhra = tombola.get(cislo_uzivatele, 'Bohužel nevyhráváš nic.')

print(f'Vyhrál jsi: {vyhra}')

tombola.pop(cislo_uzivatele)
```

---

# Bonusy

## 4 - Paranoidní večírek ◇◆◆◆◆

Pořadatel našeho večírku se stává stále více paranoidním a nyní rozhodl, že každý z hostů bude mít speciální heslo,
které je platné jen pro něj. Seznam hostů a jejich hesel je níže.  
Napiš program, který nejprve zkontroluje, zda je host na seznamu, a pokud tam je,zeptá se ho na heslo a zkontroluje jeho
správnost.  
Hostu na seznamu, který zadá správné heslo, vypíše program text: `"Smíš vstoupit."`

### Řešení

```python
hesla = {
    'Jiří'   : 'tajne-heslo',
    'Natálie': 'jeste-tajnejsi-heslo',
    'Klára'  : 'nejtajnejsi-heslo',
}

jmeno_hosta = input('Zadej jmeno: ')
vstup = 'Nesmíš projít.'

if jmeno_hosta in hesla:
    heslo = input('Zadej heslo: ')
    if heslo == hesla[jmeno_hosta]:
        vstup = 'Smíš vstoupit.'

print(vstup)
```

# Slovníky a cykly

## 1 - Vysvědčení 2 ◇◇◇◆◆

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
prumerna_znamka = sum(vysvedceni.values()) / len(vysvedceni)
print(f'Průměrná známka je: {prumerna_znamka}')

print('Předměty s jedničkou:')
for predmet, znamka in vysvedceni.items():
    if znamka == 1:
        print('\t' + predmet)
```

## 2 - Čtenářský deník ◇◇◇◆◆

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

---

# Bonusy

## 3 - Poznávací značky ◇◇◆◆◆

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

- Napiš program, který vypíše všechny majitele, jejichž vozidlo je registrováno v Plzeňském kraji.  
  tj. na druhém místě (index 1) řetězce v klíči je písmeno P.

### Řešení

```python
print('Lidé z Plzeňského kraje:')
for spz, jmeno in spzetky.items():
    if spz[1] == 'P':
        print(f'- {jmeno}')
```

## 4 - Recepty ◇◇◆◆◆

Pohlédněte na následující reprezentaci receptu:

```python
{
    'nazev'      : 'Batáty se šalvějí a pancettou',
    'narocnost'  : 'stredni',
    'doba'       : 30,
    'ingredience': [
        ['batát', '1', '15 kč'],
        ['olivový olej', '2 lžíce', '2 kč'],
        ['pancetta', '4-6 plátků', '21 kč'],
        ['přepuštěné máslo', '2 lžíce', '5 kč'],
        ['mletý černý pepř', '1/2 lžičky', '0.5 kč'],
        ['sůl', '1/2 lžičky', '0.1 kč'],
        ['muškátový oříšek', 'špetka', '1 kč'],
        ['česnek', '2 stroužky', '1 kč'],
        ['šalvějové lístky', '20-25', '12 kč']
    ]
}
```

Uložte si tuto strukturu do proměnné `recept` na začátek nového programu. Vypište pomocí funkce `print` kolik bude celé jídlo stát korun zaokrouhlené na celé koruny nahoru.

### Řešení

```python
recept = {
    'nazev'      : 'Batáty se šalvějí a pancettou',
    'narocnost'  : 'stredni',
    'doba'       : 30,
    'ingredience': [
        ['batát', '1', '15 kč'],
        ['olivový olej', '2 lžíce', '2 kč'],
        ['pancetta', '4-6 plátků', '21 kč'],
        ['přepuštěné máslo', '2 lžíce', '5 kč'],
        ['mletý černý pepř', '1/2 lžičky', '0.5 kč'],
        ['sůl', '1/2 lžičky', '0.1 kč'],
        ['muškátový oříšek', 'špetka', '1 kč'],
        ['česnek', '2 stroužky', '1 kč'],
        ['šalvějové lístky', '20-25', '12 kč']
    ]
}

celkem = 0
for ingredience in recept['ingredience']:
    cena_text = ingredience[-1]
    cena = float(cena_text.split(' ')[0])
    celkem += cena

print(f'recept stojí celkem {celkem} Kč')
```

---

# Cvičení na doma

## 1 - Spolubydlící ◇◆◆◆◆

Zkus dotáhnout náš program na finanční vypořádání spolubydlících. Z lekce si můžeš zkopírovat kódy, které vytvoří slovník s útratami jednotlivých spolubydlících a výpočet průměrné útraty na osobu.  
Dopiš cyklus, který projde slovník `sum_per_person` a pro každého ze spolubydlících vypíše, kolik by měl doplatit (pokud utratil(a) méně než průměr), případně kolik by měl obdržet (pokud utratil(a) více než průměr).

### Řešení

```python
import statistics

purchase_list = [
    {"Jméno": "Petr", "Položka": "Prací prášek", "Částka": 399},
    {"Jméno": "Ondra", "Položka": "Savo", "Částka": 80},
    {"Jméno": "Petr", "Položka": "Toaletní papír", "Částka": 65},
    {"Jméno": "Libor", "Položka": "Pivo", "Částka": 124},
    {"Jméno": "Petr", "Položka": "Pytel na odpadky", "Částka": 75},
    {"Jméno": "Míša", "Položka": "Utěrky na nádobí", "Částka": 130},
    {"Jméno": "Ondra", "Položka": "Toaletní papír", "Částka": 120},
    {"Jméno": "Míša", "Položka": "Pečící papír", "Částka": 30},
    {"Jméno": "Zuzka", "Položka": "Savo", "Částka": 80},
    {"Jméno": "Pavla", "Položka": "Máslo", "Částka": 50},
    {"Jméno": "Ondra", "Položka": "Káva", "Částka": 300}
]

# vytvoříme slovník
sum_per_person  = {}

for polozka in purchase_list:
    person = polozka['Jméno']
    value = polozka['Částka']

    # get nám dá hodnotu, pokud je ve slovníku, nebo zadanou hodnotu (zde 0)
    sum_per_person[person] = sum_per_person.get(person, 0) + value

average_value = statistics.mean(sum_per_person.values())

for person, value in sum_per_person.items():

    diff = round(value - average_value)

    if diff > 0:
        print(f'{person} dostane {diff}')
    elif diff < 0:
        print(f'{person} zaplati {abs(diff)}')
    else:
        print(f'{person} je na nule')
```