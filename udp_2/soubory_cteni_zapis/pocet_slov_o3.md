## Počet slov ◇◇◆◆◆

Stáhněte si odevzdanou slohovou práci.  
Zadání bylo sepsat text o nejméně 150ti slovech pojednávající o našem hlavním městě.  
Napište program, který spočítá počet slov v tomto textu, abychom věděli, zda bylo zadání formálně splněno. Nechte se vést následujícím návodem.

- Nechte váš program otevřít soubor a načíst jednotlivé řádky do seznamu
- Každý řádek převeďte na seznam slov. Slovem se rozumí vše, co je odděleno mezerou nebo novým řádkem
- Vypište na výstup počty slov na každém řádku
- Vypište na výstup celkový počet všech slov v souboru

### Řešení

```python
seznam_radku = []
with open(r'slohovka.txt', encoding='utf-8') as file:
    for radek in file:
        seznam_radku.append(radek.split())  # pridame rovnou rozsekany radek

celkovy_pocet_slov = 0
print('pocty radku')
for radek in seznam_radku:
    pocet_slov_v_radku = len(radek)
    print(pocet_slov_v_radku)
    celkovy_pocet_slov += pocet_slov_v_radku

print(f'celkovy pocet slov je {celkovy_pocet_slov}')
```
