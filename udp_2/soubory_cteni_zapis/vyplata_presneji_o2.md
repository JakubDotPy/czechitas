## Výplata přesněji ◇◇◇◆◆

Zatím jsme výplatu počítali za předpokladu, že každý měsíc odpracujeme stejný počet hodin, což není příliš realistické.  
Vytvořte proto textový soubor `vykaz.txt`, který bude obsahovat 12 řádků a na každém řádku počet odpracovaných hodin za každý měsíc za poslední rok.

- Otevřete tento soubor ve svém programu a načtěte hodnoty na řádcích do seznamu `vykaz`. Vytiskněte tento seznam do terminálu funkcí `print()` abyste si ověřili, že jste soubor načetli správně.
- Nechte uživatele zadat na příkazovém řádku hodinovou mzdu. Spočítejte a na výstup vytiskněte celkovou výplatu za celý rok a průměrnou výplatu na jeden měsíc.

<details>
<summary><b>Řešení</b></summary>


```python
import statistics

with open('vykaz.txt') as file:
    vykaz = []
    for hodnota in file:
        vykaz.append(int(hodnota))

print(vykaz)

hodinovka = int(input('Zadej hodinovou mzdu: '))

vyplaty = []
for pocet_hodin in vykaz:
    vyplaty.append(pocet_hodin * hodinovka)
    
print(f'Vyplata za cely rok je {sum(vyplaty)}, průměrná {statistics.mean(vyplaty)}')
```

</details>
