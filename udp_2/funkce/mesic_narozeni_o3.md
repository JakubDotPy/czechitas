## Měsíc narození

Napiš funkci `month_of_birth`, která bude mít jeden parametr - `rodne_cislo`.  
Funkce ze zadaného rodného čísla určí měsíc narození, které vrátí jako výstup. Nezapomeň, že pro ženy je k měsíci
připočtena hodnota 50.

Příklad:

- Pro hodnotu `9207054439` vrátí `7`.
- Pro hodnotu `9555125899` vrátí `5`.

<details>
<summary><b>Řešení</b></summary>


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


</details>
