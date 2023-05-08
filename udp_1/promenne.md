# Cvičení

*tyto příklady je lepší si zkoušet přímo v Python konzoli: `>>> `*  
*oficiálně ještě neznáme funkci `print()`*
*k zobrazení výsledku pak stačí napsat název proměnné*

## 1 - Hrátky s proměnnými ◇◇◇◇◆

Dbejte na to, aby proměnné měly vhodný název dobře naznačující, co je v které z nich uloženo.

- Uložte do proměnné `herci` celočíselnou hodnotu udávající počet herců, kteří hrají v divadle. Do proměnné `platy`
  spočítejte celkové náklady divadla na platy herců, víme-li, že průměrný plat herce je 22 392 Kč.
- Do jiné proměnné s vhodným názvem uložte nějaké desetinné číslo, například velikost slevy na studentské vstupné. Do
  další proměnné uložte nějaký řetězec, například název nějakého představení.
- Zatímco jste dělali předchozí cvičení, do divadla přibyli dva noví herci. Aktualizujte tedy obsah proměnné herci a
  zařiďte, aby v proměnné platy byla správná hodnota nákladů. Zamyslete se nad tím co se stalo s hodnotou, která byla v
  proměnné herci uložena před tím.

### Řešení

```python
herci = 15
platy = herci * 22_392

sleva = 0.65
predstaveni = "Romeo a Julie"

herci += 2
platy = herci * 22_392
```

*Poznámka: symbol `_` v čísle nemá žádný vedlejší efekt a můžete ho tak použít jako oddělovač tisíců pro lepší čitelnost
delších čísel.*

## 2 - Celočíselné dělení a dělení se zbytkem ◇◇◇◇◆

Zaexperimentujte s operátory celočíselného dělení a dělení se zbytkem.

- Kolikrát se vejde číslo 72 do 1024? Kolik je zbytek po dělení čísla 1024 číslem 72?
- Divadlo má délky představení vždy uloženo v minutách. Například extrémně nudné a zničující představení *Smrt v přímém
  přenosu* trvá 265 minut. Uložte tuto hodnotu do proměnné `delka`.
- Použijte proměnnou `delka` a spočítejte trvání představení vyjádřeno v hodinách a minutách. Do proměnné `hodin` uložte
  počet celých hodin a do proměnné `minut` uložte zbylé minuty.

### Řešení

```python
podil = 1024 // 72
zbytek = 1024 % 72

delka = 265

hodin = delka // 60
minut = delka % 60
```

---

# Bonusy

## 3 - Sedačky v sále ◇◇◇◆◆

Hlavní sál divadla má k dispozici 350 sedaček. Lze je poskládat do řad po 32 sedadlech tak, aby všechny řady byly úplné?
Pokud ne, kolik sedaček musíme přikoupit, aby to šlo? Kolik nám takto vznikne celkem řad?

### Řešení

```python
zbyva = 350 % 32
dokoupit = 32 - zbyva
celkem_rad = (350 + dokoupit) / 32
```

# Úlohy na doma


## 1 - Základní aritmetické operace ◇◇◇◇◆

Do proměnné `a` uložte libovolné celé číslo, do proměnné `b` uložte libovolné desetinné číslo. V následujících úlohách každý výsledek uložte do nové proměnné.

- Vypočítejte součet `a` a `b`.
- Vypočítejte součin `a` a `b`.
- Vypočítejte zbytek po dělení čísla `a` číslem `b`.
- Celočíselně vydělte číslo `a` číslem `b`.

### Řešení

```python
a = 5
b = 2.2

soucet = a + b
soucin = a * b
zbytek = a % b
celociselne_deleni = a // b
```

## 2 - Antikvariát ◇◇◇◆◆

Antikvariát *Poslední strana* nabízí veškeré své tituly za 50 kč.

- Uložte název antikvariátu do libovolné proměnné.
- Cenu za jeden titul uložte do proměnné `cena_za_kus`.
- Antikvariát má dnes speciální akci, -30% na všechny dostupné tituly! Slevu uložte do proměnné `sleva` jako desetinné číslo.
- Znovu vypočtěte cenu za kus na základě této slevy.

### Řešení

```python
nazev = 'Poslední strana'
cena_za_kus = 50
sleva = 0.3
cena_za_kus = (1 - sleva) * cena_za_kus
```

## 3 - Plánování svatby ◇◇◇◆◆

Karolína bude mít za půl roku svatbu a právě obdržela od agentury ceník služeb. Cena za kompletní menu pro dospělou osobu je 990 kč, pro dítě je to 50% ceny dospělého.

- Uložte cenu za dospělou osobu do proměnné `cena_dospely`.
- Pomocí proměnné `cena_dospely` vypočítejte cenu za dítě, tu uložte do proměnné `cena_dite`.
- Vypočítejte celkové náklady na jídlo pro 60 dospělých a 8 dětí. Pro výpočet použijte předchozí proměnné.
- V ceníku byla chyba, cena za dospělého je ve skutečnosti 1000 kč. Upravte na základě této informace všechny proměnné.

*Tip: Jednotlivé výpočty nemusíte kopírovat ani psát znovu, v terminálu stačí použít šipku nahoru.*

### Řešení

```python
cena_dospely = 990
cena_dite = cena_dospely * 0.5
naklady = 60 * cena_dospely + 8 * cena_dite

cena_dospely = 1000
cena_dite = cena_dospely * 0.5
naklady = 60 * cena_dospely + 8 * cena_dite
```