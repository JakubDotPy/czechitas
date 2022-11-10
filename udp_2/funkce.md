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

## 4 - Ruleta ♦♦♦♦♦

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
    rady = [
        range(1, 37, 3),  # 1, 4, 7, ...
        range(2, 37, 3),  # 2, 5, 8, ...
        range(3, 37, 3),  # 3, 6, 9, ...
        ]
    hozeno = random.randint(0, 36)
    print(f'{hozeno = }')
    return 2 * sazka if hozeno in rady[cislo_rady - 1] else 0  # "- 1" kvůli indexování od nuly
```


