## Balík jako datová třída ◇◇◇◆◆

Uprav třídu `Package` na datovou třídu. Třída bude mít atributy `address`, `weight`, a `state`. U `state` nastav výchozí
hodnotu jako nedoručen. U každého z atributů vymysli a nastav vhodný datový typ. Existující metody ve třídě ponech.
Neměň ani třídu `ValuablePackage`.

Následně vyzkoušej, zda funguje vytváření balíků.

<details>
<summary><b>Řešení</b></summary>


```python
from dataclasses import dataclass


@dataclass
class Package:
    address: str
    weight: float
    state: str = "nedoručen"

    def __str__(self):
        return f"Balík na adresu {self.address} má hmotnost {self.weight} kg a je ve stavu {self.state}."

    def deliver(self):
        if self.state == "doručen":
            return "Balík již byl doručen"
        else:
            self.state = "doručen"
            return "Doručení uloženo"


# Vytvoření objektů
package = Package("Jiřího z Poděbrad 9, Brno", 1.5, "doručen")

# Výpis informací o balících
print(package)

print(package.deliver())
print(package)  # Zkontrolujeme, že balík je nyní ve stavu "doručen"
print(package.deliver())  # Zkusíme znovu doručit balík
```


</details>
