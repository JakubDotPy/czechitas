## Ruleta

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

<details>
<summary><b>Řešení</b></summary>


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

</details>
