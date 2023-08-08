## Hotel ◇◇◇◆◆

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