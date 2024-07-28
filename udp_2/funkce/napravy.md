## Nápravy

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
print(pokuta)  # 2000
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

<details>
<summary><b>Řešení</b></summary>

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

</details>
