# Cvičení

## 1 - Hrátky s proměnnými ○○○○♦

Dbejte na to, aby proměnné měly vhodný název dobře naznačující, co je v které z nich uloženo.

- Uložte do proměnné herci celočíselnou hodnotu udávající počet herců, kteří hrají v divadle. Do proměnné platy
  spočítejte celkové náklady divadla na platy herců, víme-li, že průměrný plat herce je 22 392 Kč.
- Do jiné proměnné s vhodným názvem uložte nějaké desetinné číslo, například velikost slevy na studentské vstupné. Do
  další proměnné uložte nějaký řetězec, například název nějakého představení.
- Zatímco jste dělali předchozí cvičení, do divadla přibyli dva noví herci. Aktualizujte tedy obsah proměnné herci a
  zařiďte, aby v proměnné platy byla správná hodnota nákladů. Zamyslete se nad tím co se stalo s hodnotou, která byla v
  proměnné herci uložena před tím.

### Řešení

```python
herci = 15
platy = herci * 22392

sleva = 0.65
predstaveni = "Romeo a Julie"

herci += 2
platy = herci * 22392
```

## 2 - Celočíselné dělení a dělení se zbytkem ○○○○♦

Zaexperimentujte s operátory celočíselného dělení a dělení se zbytkem.

- Kolikrát se vejde číslo 72 do 1024? Kolik je zbytek po dělení čísla 1024 číslem 72?
- Divadlo má délky představení vždy uloženo v minutách. Například extrémně nudné a zničující představení “Smrt v přímém
  přenosu” trvá 265 minut. Uložte tuto hodnotu do proměnné delka.
- Použijte proměnnou delka a spočítejte trvání představení vyjádřeno v hodinách a minutách. Do proměnné hodin uložte
  počet celých hodin a do proměnné minut uložte zbylé minuty.

### Řešení

```python
podil = 1024 // 72
zbytek = 1024 % 72

delka = 265

hodin = delka // 60
minut = delka % 60
```

# Bonusy

## 3 - Sedačky v sále ○○○♦♦

Hlavní sál divadla má k dispozici 350 sedaček. Lze je poskládat do řad po 32 sedadlech tak, aby všechny řady byly úplné?
Pokud ne, kolik sedaček musíme přikoupit, aby to šlo? Kolik nám takto vznikne celkem řad?

### Řešení

```python
zbyva = 350 % 32
dokoupit = 32 - zbyva
celkem_rad = (350 + dokoupit) / 32
```
