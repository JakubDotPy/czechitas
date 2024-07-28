## Cena přepravy

Pokračuj ve své práci pro zásilkovou společnost. Společnost nově požaduje, aby náš software uměl dopočítat cenu přepravy
balíku.

- Do třídy `Package` přidej metodu `get_costs()`. Vypočítej přepravu na základě hmotnosti. Přeprava balíku do 2 kg stojí
  150 Kč, balíků mezi 2 a 5 kg 190 Kč a těžších balíků 220 Kč. Zkontroluj, zda metoda funguje i pro cenné balíky.
- U cenných balíků bude k ceně připočtení pojištění. Přidej ke třídě `ValuablePackage` metodu `get_costs()`. Ta spočítá
  cenu přepravy s využitím metody mateřské třídy `Package`. K tomu připočte pojistné ve výši 5 % ceny balíku.

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

    def get_costs(self):
        cost = 0
        if self.weight <= 2:
            cost = 150
        elif self.weight <= 5:
            cost = 190
        else:
            cost = 220
        return cost

    def deliver(self):
        if self.state == "doručen":
            return "Balík již byl doručen"

        self.state = "doručen"
        return "Doručení uloženo"


class ValuablePackage(Package):
    def __init__(self, address, weight, state, value):
        super().__init__(address, weight, state)
        self.value = value

    def __str__(self):
        return super().__str__() + f" Balíček má hodnotu {self.value} Kč."

    def get_costs(self):
        price = super().get_costs()
        return price * 1.05
```

</details>
