# Cvičení

## 1 - Násobení ○○○♦♦

Napiš funkci `mult`, která bude mít dva číselné parametry. Funkce oba parametry vynásobí a vrátí výsledek.

### Řešení

```python
def mult(a, b):
    return a * b

vysledek = mult(5, 2)
print(f'5 * 2 = {vysledek}')
```

## 2 - Hotel ○○○♦♦

Napiš funkci `total_price`, která vypočte cenu noci v hotelu. Funkce bude mít dva parametry - `people`
a `breakfast`.  
Cena za noc za osobu je `850 Kč` a cena za snídani za osobu je `125 Kč`.  
Funkce vrátí výslednou cenu. Parametr `breakfast` je nepovinný a výchozí hodnota je `False`.

Funkci vyzkoušej se zadáním dvou i jedné hodnoty, např. `total_price(3)`, `total_price(2, True)`.

### Řešení

```python
def total_price(people, breakfast=False):
    cena_za_noc = 850
    cena_za_snidani = 125

    celkem = cena_za_noc * people

    if breakfast:
        celkem += cena_za_snidani * people

    return celkem

print(f'Cena za tři lidi: {total_price(3)}')
print(f'Cena za dva lidi se snidani: {total_price(2, True)}')
```

## 3 - Rámeček ○○♦♦♦

Napiš funkci, která jako parametr převezme řetězec a vytiskne jej obalen hvězdičkami.

```text
Zadej slovo: ahoj
********
* ahoj *
********
```

### Řešení

```python
def ramecek(slovo):
    delka = len(slovo)
    sirka_ramecku = delka + 4  # chceme trochu mista kolem slova
    print('*' * sirka_ramecku)
    print(f'* {slovo} *')
    print('*' * sirka_ramecku)

s = input('Zadej slovo: ')
ramecek(s)
```

# Bonusy

## 3 - Měsíc narození ○○♦♦♦

Napiš funkci `month_of_birth`, která bude mít jeden parametr - `rodne_cislo`.  
Funkce ze zadaného rodného čísla určí měsíc narození, které vrátí jako výstup. Nezapomeň, že pro ženy je k měsíci
připočtena hodnota 50.

Příklad:

- Pro hodnotu `9207054439` vrátí `7`.
- Pro hodnotu `9555125899` vrátí `5`.

### Řešení

```python
def month_of_birth(rodne_cislo):
    cislo_mesice = int(str(rodne_cislo)[2:4])
    if cislo_mesice <= 12:
        return cislo_mesice
    else:
        return cislo_mesice - 50

print(f'9207054439 -> {month_of_birth(9207054439)}')
print(f'9555125899 -> {month_of_birth(9555125899)}')
```

## 5 - Zarovnání výpisu ○♦♦♦♦

Vypište seznam čísel každé na nový řádek zarovnané vpravo na délku nejdelšího čísla.

```python
numbers = [7728, 88, 958621, 5941, 959847272, 3944, 80, 521, 57035, 3967894]
```

Návod: Zjistěte kolik znaků zabírá nejdelší číslo ze seznamu
Napište funkci, která dostane řetězec a délku, na kterou má text vyplnit zleva mezerami

Bonus: funkce bude mít volitelný parametr, jakým znakem má text vyplňovat

Výstup:

```text
     7728
       88
   958621
     5941
959847272
     3944
       80
      521
    57035
  3967894
```

Výstup bonusu:

```text
.....7728
.......88
...958621
.....5941
959847272
.....3944
.......80
......521
....57035
..3967894
```

### Řešení

```python
def zarovnej(retezec, delka, znak=' '):
    zleva = delka - len(retezec)
    print(znak * zleva + retezec)

nejdelsi = 0
for n in numbers:
    aktualni_delka = len(str(n))
    if aktualni_delka > nejdelsi:
        nejdelsi = aktualni_delka

# ted uz jen pomoci funkce vypiseme
for n in numbers:
    zarovnej(str(n), nejdelsi)

# a jako bonus
for n in numbers:
    zarovnej(str(n), nejdelsi, '.')
```

## 6 - Ruleta ♦♦♦♦♦

Napiš funkci, která bude jednoduchou simulací rulety. Budeme uvažovat pouze možnost sázení na řady. Uživatel si může
vybrat jednu ze tří řad:

- první řada (hodnoty 1, 4, 7 atd.),
- druhá řada (hodnoty 2, 5, 8 atd.),
- třetí řada (hodnoty 3, 6, 9 atd.).
- Zeptej se uživatele, na kterou ze tří řad sází a na výši sázky.
- Vytvoř funkci `roulette`, která bude mít parametry `cislo_rady` a `sazka`. Pomocí funkce `randint` z modulu `random`
  vygeneruj náhodné číslo v rozsahu od 0 (včetně) do 36. Vyhodnoť, do které řady číslo náleží. Nezapomeň, že 0 nepatří
  do žádné z řad a pokud padne, uživatel vždy prohrává.
- Funkce `roulette` vrací hodnotu výhry. Pokud uživatel vsadil na správnou řadu, vyhrává dvojnásobek sázky, v opačném
  případě nevyhrává nic jeho sázka propadá.

### Řešení

```python
import random

cislo_rady = int(input('Na kterou řadu sázíš? (1-3): '))
sazka = int(input('Kolik sázíš?: '))

def roulette(cislo_rady, sazka):

    # pouzijeme funkci range na vytvoreni seznamu cisel
    rady = [
        range(1, 37, 3),  # 1, 4, 7, ...
        range(2, 37, 3),  # 2, 5, 8, ...
        range(3, 37, 3),  # 3, 6, 9, ...
    ]
    hozeno = random.randint(0, 36)
    print(f'hozeno: {hozeno}')
    return 2 * sazka if hozeno in rady[cislo_rady - 1] else 0  # "- 1" kvůli indexování od nuly
```

## 7 - Zpřeházená písmena ○♦♦♦♦

Slovo je stále možné pohodlně přečíst, když jsou pomíchaná písmena. Stačí, když první a poslední písmeno je na své
pozici zachováno. Napiš funkci, která bude mít jako vstupní parametr slovo a vrátí slovo, kde zpřehází všechny znaky
kromě prvního a posledního.

Nápověda: `random.shuffle()`

Super bonus: Napiš program, který takovou funkci využije na delší text více slov.

### Řešení

```python
import random

def zamichej_slovo(slovo):
    pismena_jako_list = list(slovo)
    stred = pismena_jako_list[1:-1]
    random.shuffle(stred)
    return slovo[0] + ''.join(stred) + slovo[-1]

print(zamichej_slovo('lokomotiva'))

text = '''Slovo je stále možné pohodlně přečíst, když jsou pomíchaná písmena.
Stačí, když první a poslední písmeno je na své pozici zachováno. Napiš funkci,
která bude mít jako vstupní parametr slovo a vrátí slovo, kde zpřehází všechny
znaky kromě prvního a posledního.
'''

zamichana_slova = []
for slovo in text.split():
    zamichana_slova.append(zamichej_slovo(slovo))

vysledny_text = ' '.join(zamichana_slova)
print(vysledny_text)
```

## 8 - Nápravy ○♦♦♦♦

Náprava je část vozidla, která spojuje kola s karosérií vozidla. U nákladních vozidel ho můžeme chápat jako počet "
dvojic kol". Počet náprav je důležitý napříkad kvůli maximální povolené hmotnosti vozidla.

Uvažuj limity pro maximální hmotnost nákladního vozidla, které jsou v tabulce níže.

| Počet náprav | Maximální dovolená hmotnost v tunách |
|--------------|--------------------------------------|
| 2            | 18                                   |
| 3            | 25                                   |
| 4            | 32                                   |
| 5            | 48                                   |

Pokud je limit překročen, platí provozovatel pokutu 1000 Kč za každou tunu, o které je vozidlo těžší. Například pokud má
vozidlo 4 nápravy a hmotnost 34 tun, platí provozovatel pokutu 2000 Kč.  
Napiš funkci `spocitej_pokutu()`, která bude mít dva parametry - `pocet_naprav` (počet náprav vozidla) a `hmotnost` (
hmotnost vozidla v tunách).  
Funkce na základě těchto parametrů vypočte výpiš pokuty a vráti ji jako celé číslo.

```python
pokuta = spocitej_pokutu(4, 34)
print(pokuta) # 2000
```

Dále uvažuj následující dvourozměrný seznam, kde na prvním místě vnořeného seznamu je počet náprav vozidla a na druhém
místě je zjištěná hmotnost.

```python
vazeni = [
    [4, 33],
    [2, 19],
    [3, 29],
    [3, 27],
    [5, 53],
    [5, 51],
    [2, 20],
]
```

Projdi seznam pomocí cyklu a pro každé vážení urči (s využitím funkce spocitel_pokutu()) výši pokuty. Spočítej celkovou
výši pokut za všechna vážení.

### Řešení

```python
def spocitej_pokutu(pocet_naprav, hmotnost):
    # oficialne jestli nezname slovnik,
    # musime rozdelit pomoci podminek
    if pocet_naprav == 2:
        max_hmotnost = 18

    if pocet_naprav == 3:
        max_hmotnost = 25

    if pocet_naprav == 4:
        max_hmotnost = 32

    if pocet_naprav == 5:
        max_hmotnost = 48

    # musime omezit nulou aby nebyly zaporne pokuty
    prekrocena_hmotnost = min([hmotnost - max_hmotnost, 0])

    return 1000 * prekrocena_hmotnost


for data in vazeni:
    pokuta = spocitej_pokutu(data[0], data[1])
    print(f'dostavas pokutu {pokuta}')
```
