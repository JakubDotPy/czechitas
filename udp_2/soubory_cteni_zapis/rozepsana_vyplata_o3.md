## Rozepsaná výplata

Modifikujte program pro počítání výplaty z předchozí sekce tak, aby nevypisoval průměrnou výplatu za rok, nýbrž aby vypsal konkrétní vyplacenou částku pro každý měsíc zvlášť.

- Nejprve tyto informace vypište na terminál
- Poté program upravte tak, aby vypsal tyto výsledky do souboru

<details>
<summary><b>Řešení</b></summary>


```python
hodinovka = int(input('Zadej hodinovou mzdu: '))

# muzeme si otevrit oba soubory zaroven
with open('vykaz.txt') as vstupni_soubor:
    with open('vystup.txt', 'w') as vystup:
        for hodnota in vstupni_soubor:
            print(int(hodnota) * hodinovka, file=vystup)
```

</details>
