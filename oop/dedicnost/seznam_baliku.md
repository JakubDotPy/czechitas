## Seznam balíků

Pokračuj ve své práci pro zásilkovou společnost. Společnost chce doplnit do aplikace funkci pro výpočet celkového
hodnoty nákladu nějakého auta, aby pak (např. v případě nehody nebo krádeže) mohla snadno spočítat celkovou hodnotu
cenných balíků v autě a předat informaci pojišťovně.

```python
package_1 = ValuablePackage("Grimmauldovo náměstí 11", 1.9, "nedoručen", 5500)
package_2 = Package("Godrikův důl 47", 1.9, "nedoručen")
package_3 = ValuablePackage("Vydrník svatého Drába 13", 1.9, "nedoručen", 5500)
package_list = [package_1, package_2, package_3]
```

- Vytvoř si proměnnou `total_value`, do které si s využitím cyklu budeš ukládat celkovou hodnotu všech balíků. Na
  začátku bude mít hodnotu 0.
- Vytvoř cyklus, který projde seznam `package_list`.
- Pro každý objekt ze seznamu nejprve zkontroluje, zda má atribut `value`. Pokud ano, připočti hodnotu balíku k
  proměnné `total_value`.
- Na konci programu vypiš, jaká je celková hodnota balíků v autě.

<details>
<summary><b>Řešení</b></summary>

```python
package_1 = ValuablePackage("Grimmauldovo náměstí 11", 1.9, "nedoručen", 5500)
package_2 = Package("Godrikův důl 47", 1.9, "nedoručen")
package_3 = ValuablePackage("Vydrník svatého Drába 13", 1.9, "nedoručen", 5500)
package_list = [package_1, package_2, package_3]

total_value = 0

for package in package_list:
    if hasattr(package, 'value'):
        total_value = total_value + package.value

print(f"Celková hodnota balíků v autě je {total_value} Kč.")
```

</details>
