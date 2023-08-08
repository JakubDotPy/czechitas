## Balík potřetí ◇◇◇◇◆

Vrať se k návrhu software pro zásilkovou společnost. U třídy `Package` uprav atribut `state` tak, aby byl chráněný.
Ověř, že vytváření objektů i výpisy informací o něm fungují.

### Řešení

```python
class Package:
    def __init__(self, address, weight, state="nedoručen"):
        self.address = address
        self.weight = weight
        self._state = state

    def __str__(self):
        return f"Balík na adresu {self.address} má hmotnost {self.weight} kg a je ve stavu {self._state}."

    def deliver(self):
        if self._state == "doručen":
            return "Balík již byl doručen"
        else:
            self._state = "doručen"
            return "Doručení uloženo"


# Vytvoření objektů
package1 = Package("Václavské Náměstí 12, Praha", 0.25, "nedoručen")

# Výpis informací o balících
print(package1)

# Vyzkoušení metody deliver
print(package1.deliver())
print(package1)  # Zkontrolujeme, že balík je nyní ve stavu "doručen"
print(package1.deliver())  # Zkusíme znovu doručit balík
```