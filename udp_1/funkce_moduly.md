# Cvičení

## 1 - Délka názvu ◇◇◇◇◆

Uložte si do proměnné nazev řetězec s názvem *Divadlo Pěst na oko*. Pokud použijeme designové písmo nad hlavní vchod
budovy, jeden znak (i mezera) bude široký 30 cm. Použijte funkci `len()` abyste zjistili počet znaků v názvu divadla a
spočítejte délku nápisu v centimetrech.

### Řešení

```python
nazev = "Divadlo Pěst na oko"
delka = len(nazev) * 30
```

## 2 - Zaokrouhlování ◇◇◇◆◆

Divadlo chce mít ceny vstupenek jak v eurech tak v celých korunách. Uložte do proměnné `eura` cenu studentské vstupenky(
65 % z 12 euro). Použijte funkci `round()` a do proměnné `koruny` spočítejte, kolik činí studentské vstupné v korunách
jestliže, kurz eura je 24 korun.

### Řešení

```python
eura = 12 * 0.65
koruny = round(24 * eura)
```

## 3 - Zaokrouhlování nahoru ◇◇◇◇◆

Importujte modul `math` a vyzkoušejte si funkci `math.ceil()`, která slouží k zaokrouhlování směrem nahoru. Proveďte
zaokrouhlování z předchozího cvičení na celé koruny směrem nahoru.

### Řešení

```python
import math

eura = 12 * 0.65
koruny = math.ceil(24 * eura)
```

## 4 - Náhodná čísla ◇◇◇◆◆

Na informačním panelu v předsálí divadla se zobrazují informace o náhodných představeních. Pro tento panel potřebujeme
generátor náhodných čísel, který bude generovat čísla představení mezi 1 až 24. Importujte modul `random` a použijte
funkci `randint()` pro vygenerování několika náhodných čísel z tohoto rozsahu.

### Řešení

```python
import random

cislo = random.randint(1, 24)
```

---

# Cvičení na doma


## 1 - Klasické zaokrouhlování[^1] ◆◆◆◆◆

Překvapivě Python neobsahuje[^2] žádnou funkci, která by dělala klasické zaokrouhlování, tedy takové, na které jsme
všichni zvyklí ze školy. S něčím takovým se nemůžeme spokojit.

- Zkuste vymyslet (za použití funkcí, které už znáte) příkaz, který zaokrouhlí číslo v proměnné `cislo` na celé číslo
  klasickým zaokrouhlováním.

- Pokud si chcete svoje řešení otestovat, můžete si obsah proměnné `cislo` vygenerovat náhodně funkcí `random.uniform()`
  . Ta má stejné vstupy jako funkce `random.randint()`, generuje ale desetinná čísla.

[^1]: Tento příklad se dá považovat za zajímavost, protože klasické zaokrouhlování `round` zaokrouhluje hraniční případy
2.5, 3.5, ... vždy k *nejbližšímu sudému celému číslu*.  
[^2]: Python tuto funkci samozřejmě obsahuje. Hned několik zaokrouhlovacích funkcí najdete v
modulu [`decimal`](https://docs.python.org/3/library/decimal.html#rounding-modes)

### Řešení

```python
import math
import random

cislo = 2.5
zaokrouhlene = math.floor(cislo + 0.5)

cislo = random.uniform(0, 10)
zaokrouhlene = math.floor(cislo + 0.5)
```