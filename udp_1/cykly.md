# Cvičení

## 1 - Seznam hodnocení ○○○○♦

Mějme seznam hodnocení divadelní hry *Plyšáci na útěku*, který vypadá takto:
`hodnoceni = [7, 9, 6, 7, 9, 8]`  
Vytvořte program, který projde tento seznam a vypíše každé hodnocení na nový řádek. Upravte program tak, aby vypisoval
výstup v tomto formátu:

    7/10
    9/10
    6/10
    7/10
    9/10
    8/10

### Řešení

```python
hodnoceni = [7, 9, 6, 7, 9, 8]
for prvek in hodnoceni:
    print(f"{prvek}/10")
```

## 2 - Procházení seznamu ○♦♦♦♦

Založte si program `hesla.py` a na jeho začátek vložte následující kód obsahující seznam hesel pro přihlášení do
nějakého systému

```python
hesla = [
    "xyz101",
    "punťa",
    "razor-blade",
    "1234",
    "12011986",
    "martin111",
    "trhnisi",
    "hokuspokus",
    "jeník15",
    "kristus-te-spasi",
    "beruška",
    "strčprstskrzkrk",
    ]
```

- Pomocí cyklu vypište všechny hesla na obrazovku, každé na jeden řádek.
- Upravte váš program tak, aby vypisoval jen bezpečná hesla, tedy taková, jež jsou delší než 8 znaků.
- Upravte váš program tak, aby vypisoval jen ta hesla, jež obsahují znak pomlčky `-`.

### Řešení

```python
# hesla.py

# Pomocí cyklu vypište všechny hesla na obrazovku, každé na jeden řádek.
for heslo in hesla:
    print(heslo)

# Upravte váš program tak, aby vypisoval jen bezpečná hesla, tedy taková, jež jsou delší než 8 znaků.
for heslo in hesla:
    if len(heslo) > 8:
        print(heslo)

# Upravte váš program tak, aby vypisoval jen ta hesla, jež obsahují znak pomlčky ‘-’.
for heslo in hesla:
    if "-" in heslo:
        print(heslo)
```

## 3 - Složitější seznam ○○○○♦

Založte si program `cykly_02.py` a použijte v něm následující seznam měsíců v roce. Všimněte si, že je to seznam
seznamů.

```python
mesice = [
    ["leden", 31],
    ["únor", 28],
    ["březen", 31],
    ["duben", 30],
    ["květen", 31],
    ["červen", 30],
    ["červenec", 31],
    ["srpen", 31],
    ["září", 30],
    ["říjen", 31],
    ["listopad", 30],
    ["prosinec", 31],
    ]
```

- Pomocí cyklu projděte tento seznam a vypište na výstup názvy jednotlivých měsíců.
- Pomocí dalšího cyklu vypište na výstup počty dní v jednotlivých měsících.

### Řešení

```python
# cykly_02.py

# Pomocí cyklu projděte tento seznam a vypište na výstup názvy jednotlivých měsíců.
for mesic in mesice:
    print(mesic[0])
    
# Pomocí dalšího cyklu vypište na výstup počty dní v jednotlivých měsících.
for mesic in mesice:
    print(mesic[1])
```

# Bonusy

## 4 - Hry ○○♦♦♦

Následující seznam obsahuje seznam všech divadelních her, které se hrají v divadle Pěst na oko. Každá hra má svůj název
a trvání v minutách.

```python
hry = [
    ["Ňadro na ňadru na nádru", 180],
    ["Útok plyšových krokodýlů", 95],
    ["Cesta do říše zelí", 128],
    ["Romance na zdymadle", 144],
    ["Zátiší s mimozemšťanem", 135],
    ["Čtyři facky a dortík", 100],
    ["Motorová okurka", 165],
    ["Johnny Noir", 140],
    ["Pražská kavárna vrací úder", 130],
    ["Pět sester ve vratech", 111],
    ["Stařec a krajta", 187],
    ["Růžová nemoc", 210],
    ["Smrt v přímém přenosu", 265],
    ]
```

- Pomocí cyklu projděte tento seznam a vypište na výstup názvy všech her.
- Vypište na výstup názvy všech her, které trvají více než 120 minut.
- Vypište na výstup názvy všech her spolu s jejich trváním v hodinách a minutách.

### Řešení

```python
# Pomocí cyklu projděte tento seznam a vypište na výstup názvy všech her.
for hra in hry:
    print(hra[0])

# Vypište na výstup názvy všech her, které trvají více než 120 minut.
for hra in hry:
    if hra[1] > 120:
        print(hra[0])

# Vypište na výstup názvy všech her spolu s jejich trváním v hodinách a minutách.
for hra in hry:
    print(f"{hra[0]} trvá {hra[1] // 60} hodin a {hra[1] % 60} minut.")
```

## 5 - Průměr ○○○♦♦

Napište cyklus, který projde zadaný seznam desetinných čísel a spočítá jejich průměr. Seznam čísel si vytvořte na
začátku programu.

### Řešení

```python
cisla = [10.5, 13.3, 17.2, 11.5]
soucet = 0
for cislo in cisla:
    soucet += cislo
prumer = soucet / len(cisla)
print(prumer)
```

## 6 - Největší prvek ○○♦♦♦

Napište cyklus, který projde zadaný seznam celých čísel a najde v něm největší hodnotu.

### Řešení

```python
cisla = [11, 23, 45, 1, 9, 65, 34]
nejvetsi = cisla[0]
for cislo in cisla:
    if cislo > nejvetsi:
        nejvetsi = cislo
print(nejvetsi)
```