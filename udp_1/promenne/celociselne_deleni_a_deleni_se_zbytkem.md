## Celočíselné dělení a dělení se zbytkem

Zaexperimentujte s operátory celočíselného dělení a dělení se zbytkem.

- Kolikrát se vejde číslo 72 do 1024? Kolik je zbytek po dělení čísla 1024 číslem 72?
- Divadlo má délky představení vždy uloženo v minutách. Například extrémně nudné a zničující představení *Smrt v přímém
  přenosu* trvá 265 minut. Uložte tuto hodnotu do proměnné `delka`.
- Použijte proměnnou `delka` a spočítejte trvání představení vyjádřeno v hodinách a minutách. Do proměnné `hodin` uložte
  počet celých hodin a do proměnné `minut` uložte zbylé minuty.

<details>
<summary><b>Řešení</b></summary>

```python
podil = 1024 // 72
zbytek = 1024 % 72

delka = 265

hodin = delka // 60
minut = delka % 60
```

</details>
