# Cvičení

## 1 - Jednoduchá aritmetika ○○○○♦

Použijte Python konzoli jako kalkulačku:

- Jeden lístek do divadla “Pěst na oko” stojí 12 euro. Spočítejte měsíční příjem divadla ze vstupného přichází-li
  průměrně 174 návštěvníků na jedno představení a divadlo hraje 15 představení měsíčně.
- Divadlo se rozhodlo prodávat studentské vstupné ve výši 65% plného vstupného. Jak se změní měsíční příjem divadla
  pokud víme, že polovina návštěvníků jsou studenti?

### Řešení

```python
12 * 174 * 15
```

```python
((12 * 174 / 2) + (12 * 0.65 * 174 / 2)) * 15
```

## 2 - Hrátky s řetězci ○○○♦♦

- Vytvořte řetězec obsahující jméno divadla.
- Vytvořte řetězec obsahující jméno divadla tak, že sečtete dohromady jednotlivá slova toho jména.
- Zkuste vynásobit řetězec celým číslem. Jaký jste dostali výsledek?
- Vytvořte řetězec který vypadá takto: ‘111111000000’, ale místo šesti jedniček a šesti nul obsahuje 256 jedniček a 256
  nul.

### Řešení

```python
'Divadlo Pěst na oko'
```

```python
'Divadlo ' + 'Pěst ' + 'na ' + 'oko'
```

```python
'Divadlo Pěst na oko ' * 5
```

```python
'1' * 256 + '0' * 256
```

# Bonusy

## 3 - Úroky ○○♦♦♦

Fíha banka a.s. nabízí na svých stránkách spořící účet s úrokem 2,4%.  
Když si na takový účet uložíte 1 000 000 kč, kolik peněz nastřádáte za 10 let?

### Řešení

```python
1000000 * (1 + 0.024) ** 10
```

## 4 - Nový koberec ○○♦♦♦

Do malého sálu v divadle, který má tvar čtverce o rozloze 30 m^2^ potřebujeme koupit nový koberec. Jakou délku má mít
strana koberce? Vejde se nám srolovaný do dodávky s nákladovým prostorem dlouhým 5m?

### Řešení

```python
30 ** 0.5
```

Nevejde

## 5 - Shannonovo číslo ○○♦♦♦

- Takzvané Shannonovo číslo má hodnotu 10^120^ a udává kolik nejméně lze odehrát různých šachových partií. Vytvořte
  řetězec, který obsahuje toto číslo zapsané běžným způsobem pomocí cifer. Například 10^3^ je 1000, 10^6^ je 1000000
  atd.
- Čísla s mnoha nulami je v Česku zvykem zapisovat tak, že každé tři nuly následuje mezera. Jeden milión se tedy zapíše
  jako 1 000 000. Vytvořte řetězec, který obsahuje Shannonovo číslo z předchozího cvičení zapsané v tomto formátu.

### Řešení

```python
'1' + '0' * 120
```

```python
'1' + '000 ' * (120 // 3)
```
