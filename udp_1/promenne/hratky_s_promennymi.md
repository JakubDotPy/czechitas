## Hrátky s proměnnými

Dbejte na to, aby proměnné měly vhodný název dobře naznačující, co je v které z nich uloženo.

- Uložte do proměnné `velikost_souboru` celočíselnou hodnotu udávající počet herců, kteří hrají v divadle.  
  Do proměnné `platy` spočítejte celkové náklady divadla na platy herců, víme-li, že průměrný plat herce je 22 392 Kč.
- Do jiné proměnné s vhodným názvem uložte nějaké desetinné číslo, například velikost slevy na studentské vstupné. Do
  další proměnné uložte nějaký řetězec, například název nějakého představení.
- Zatímco jste dělali předchozí cvičení, do divadla přibyli dva noví herci. Aktualizujte tedy obsah
  proměnné `velikost_souboru` a zařiďte, aby v proměnné `platy` byla správná hodnota nákladů.

<details>
<summary><b>Řešení</b></summary>

```python
velikost_souboru = 15
platy = velikost_souboru * 22_392

sleva = 0.65
predstaveni = "Romeo a Julie"

velikost_souboru += 2
platy = velikost_souboru * 22_392
```

</details>
