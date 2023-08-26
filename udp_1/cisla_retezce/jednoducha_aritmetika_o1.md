## Jednoduchá aritmetika ◇◇◇◇◆

Použijte Python konzoli jako kalkulačku:

- Jeden lístek do divadla “Pěst na oko” stojí 12 euro. Spočítejte měsíční příjem divadla ze vstupného přichází-li
  průměrně 174 návštěvníků na jedno představení a divadlo hraje 15 představení měsíčně.
- Divadlo se rozhodlo prodávat studentské vstupné ve výši 65% plného vstupného. Jak se změní měsíční příjem divadla
  pokud víme, že polovina návštěvníků jsou studenti?

<details>
<summary><b>Řešení</b></summary>


```python
print(12 * 174 * 15)
```

```python
print(((12 * 174 / 2) + (12 * 0.65 * 174 / 2)) * 15)
```

</details>
