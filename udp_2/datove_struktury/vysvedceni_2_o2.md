## Vysvědčení 2 ◇◇◇◆◆

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

<details>
<summary><b>Řešení</b></summary>


```python
prumerna_znamka = sum(vysvedceni.values()) / len(vysvedceni)
print(f'Průměrná známka je: {prumerna_znamka}')

print('Předměty s jedničkou:')
for predmet, znamka in vysvedceni.items():
    if znamka == 1:
        print('\t' + predmet)
```

</details>
