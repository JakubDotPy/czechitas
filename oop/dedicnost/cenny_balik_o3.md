## Cenný balík ◇◇◆◆◆

Pokračuj ve své práci pro zásilkovou společnost. Společnost nově doručuje i cenné balíky, které mají zadanou určitou
hodnotu.

- Vytvoř třídu `ValuablePackage`, která dědí od třídy `Package`. `ValuablePackage` má navíc atribut `value`, ostatní
  atributy dědí od třídy `Package`.
- Atribut `value` nastav pomocí funkce `__init__`. Ostatní parametry předej funkci `__init__` třídy `Package`.
- Přidej do výpisu informací o cenném balíku (metoda `__str__`) informaci o ceně balíku.
- Vytvoř si alespoň jeden objekt a zkus volání jeho funkcí. Současně si vytvoř "obyčejný" balík o zkontroluj, že u něj
  se nic nezměnilo.

<details>
<summary><b>Řešení</b></summary>


```py
class ValuablePackage(Package):
    def __init__(self, address, weight, value, state="nedoručen"):
        super().__init__(address, weight, state)
        self.value = value

    def __str__(self):
        return super().__str__() + f"Balík má hodnotu hodnotu {self.value} Kč."


# Vytvoření objektů
valuable_package = ValuablePackage("Václavské Náměstí 12, Praha", 0.25, 5000)
package = Package("Jiřího z Poděbrad 9, Brno", 1.5, "doručen")

# Výpis informací o balících
print(valuable_package)
print(package)

print(valuable_package.deliver())
print(valuable_package)  # Zkontrolujeme, že balík je nyní ve stavu "doručen"
print(valuable_package.deliver())  # Zkusíme znovu doručit balík
```

</details>
