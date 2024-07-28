## Balík podruhé

Vrať se k návrhu software pro zásilkovou společnost.

- U třídy `Package` přejmenuj metodu `get_info()` na `__str__()` a vyzkoušej, jestli nyní stačí k získání informací o
  balíku funkce `print()`.
- Přidej metodu `deliver()`. Půjde o obdobu tlačítka, které řidič nebo řidička zmáčkne při doručení balíku a zaznamená
  tak jeho doručení. Metoda nejprve zkontroluje, zda balík náhodou již není ve stavu `doručen`. Pokud ano, metoda vrátí
  zprávu "Balík již byl doručen". Tím bude řidič (řidička) informován(a) o tom, že se pravděpodobně spletl(a) a snaží se
  zaznamenat doručení u špatného balíku. Pokud balík není ve stavu `doručen`, změň jeho stav právě na `doručen` a vrať
  zprávu "Doručení uloženo".
- Vyzkoušej metodu `deliver()`. Co se stane, pokud ji u jednoho balíku zavoláš dvakrát?

<details>
<summary><b>Řešení</b></summary>


```python
class Package:
    def __init__(self, address, weight, state):
        self.address = address
        self.weight = weight
        self.state = state

    def __str__(self):
        return f"Balík na adresu {self.address} má hmotnost {self.weight} kg a je ve stavu {self.state}."

    def deliver(self):
        if self.state == "doručen":
            return "Balík již byl doručen"
        else:
            self.state = "doručen"
            return "Doručení uloženo"


# Vytvoření objektů
package1 = Package("Václavské Náměstí 12, Praha", 0.25, "nedoručen")
package2 = Package("Jiřího z Poděbrad 9, Brno", 1.5, "doručen")

# Výpis informací o balících
print(package1)
print(package2)

# Zkouška metody deliver
print(package1.deliver())
print(package1)  # Balík by měl být nyní ve stavu "doručen"
print(package1.deliver())  # Metoda by nyní měla vrátit zprávu, že balík již byl doručen
```


</details>
