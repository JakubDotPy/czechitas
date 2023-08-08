# Cvičení: Dědičnost

## 1 - Cenný balík ◇◇◆◆◆

Pokračuj ve své práci pro zásilkovou společnost. Společnost nově doručuje i cenné balíky, které mají zadanou určitou
hodnotu.

- Vytvoř třídu `ValuablePackage`, která dědí od třídy `Package`. `ValuablePackage` má navíc atribut `value`, ostatní
  atributy dědí od třídy `Package`.
- Atribut `value` nastav pomocí funkce `__init__`. Ostatní parametry předej funkci `__init__` třídy `Package`.
- Přidej do výpisu informací o cenném balíku (metoda `__str__`) informaci o ceně balíku.
- Vytvoř si alespoň jeden objekt a zkus volání jeho funkcí. Současně si vytvoř "obyčejný" balík o zkontroluj, že u něj
  se nic nezměnilo.

### Řešení

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

---

# Bonusy

## 2 - Jízdenky a letenky ○♦♦♦♦

Nyní je naším cílem práce pro společnost, která se zabývá prodejem jízdenek a letenek.

- Vytvoř třídu `Ticket`, která bude mít atributy `basic_price` (základní cena) a `seat_number` (číslo sededla). Tato
  třída bude sloužit například pro cesty autobusem.
- Při cestování vlakem musíme řešit, jestli cestující využívá 1. nebo 2. třídu. Vytvoř třídu `TrainTicket`, která bude
  mít navíc atribut `fare_class` (uvažujeme možnosti `economy` a `business`). Dále naprogramuj metodu `get_price()`,
  která bude vracet hodnotu stejnou jako `basic_price`, pokud atribut `fare_class` je `economy`, a cenu o 20 % vyšší
  oproti `basic_price`, pokud `fare_class` je `business`.
- U letenek řešíme třídu, kterou cestující letí, navíc ale musíme řešit i počet odbavených zavazadel. Vytvoř
  třídu `PlaneTicket`, která bude dědit od třídy `TrainTicket` a bude mít navíc atribut `checkout_luggages`, který udává
  počet odbavených zavazadel. Naprogramuj metodu `get_price()`, která bude vracet hodnotu stejnou jako `basic_price`,
  pokud atribut `fare_class` je `economy`, a cenu o 50 % vyšší oproti `basic_price`, pokud `fare_class` je `business`.
  Dále připočti 2000 za každé odbavené zavazadlo (bez ohledu na třídu).
- Vytvoř jízdenku na vlak se základní cenou 150 do tříd `economy` i `business`. Zkontroluj, jakou hodnotu vrací
  metoda `get_price()`.
- Vytvoř letenku se základní cenou 6000 do tříd `economy` i `business` s jedním odbaveným zavazadlem. Zkontroluj, jakou
  hodnotu vrací metoda `get_price()`.

### Řešení

```python
class Ticket:
    def __init__(self, basic_price, seat_number):
        self.basic_price = basic_price
        self.seat_number = seat_number


class TrainTicket(Ticket):
    def __init__(self, basic_price, seat_number, fare_class):
        super().__init__(basic_price, seat_number)
        self.fare_class = fare_class

    def get_price(self):
        if self.fare_class == 'economy':
            return self.basic_price
        elif self.fare_class == 'business':
            return self.basic_price * 1.2


class PlaneTicket(TrainTicket):
    def __init__(self, basic_price, seat_number, fare_class, checkout_luggages):
        super().__init__(basic_price, seat_number, fare_class)
        self.checkout_luggages = checkout_luggages

    def get_price(self):
        luggage_price = self.checkout_luggages * 2000
        if self.fare_class == 'economy':
            return self.basic_price + luggage_price
        elif self.fare_class == 'business':
            return self.basic_price * 1.5 + luggage_price


# Testování:
train_ticket_economy = TrainTicket(150, '1A', 'economy')
train_ticket_business = TrainTicket(150, '1A', 'business')
print(train_ticket_economy.get_price())  # 150
print(train_ticket_business.get_price())  # 180

plane_ticket_economy = PlaneTicket(6000, '15B', 'economy', 1)
plane_ticket_business = PlaneTicket(6000, '15B', 'business', 1)
print(plane_ticket_economy.get_price())  # 8000
print(plane_ticket_business.get_price())  # 11000
```

## 3 - Cena přepravy ○○♦♦♦

Pokračuj ve své práci pro zásilkovou společnost. Společnost nově požaduje, aby náš software uměl dopočítat cenu přepravy
balíku.

- Do třídy `Package` přidej metodu `get_costs()`. Vypočítej přepravu na základě hmotnosti. Přeprava balíku do 2 kg stojí
  150 Kč, balíků mezi 2 a 5 kg 190 Kč a těžších balíků 220 Kč. Zkontroluj, zda metoda funguje i pro cenné balíky.
- U cenných balíků bude k ceně připočtení pojištění. Přidej ke třídě `ValuablePackage` metodu `get_costs()`. Ta spočítá
  cenu přepravy s využitím metody mateřské třídy `Package`. K tomu připočte pojistné ve výši 5 % ceny balíku.

### Řešení

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

--- 

# Cvičení: Dědičnost

## 1 - Seznam balíků ○○♦♦♦

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

### Řešení

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

## 2 - Seznam balíků podruhé ○○♦♦♦

Vedení společnosti si uvědomilo, že do hodnoty balíků v autě by se neměly započítávat balíky, které už byly doručeny,
protože již byly předány příjemci a nebudou tedy ukradeny nebo zničeny.

- Uprav kód, který vytváří balíky, aby byl jeden balík vytvořený ve stavu `doručen`.
- Uprav cyklus, aby započítal hodnotu pouze těch balíků, které jsou ve stavu `nedoručen`. Je třeba k této kontrole
  využít funkci `hasattr()`?

### Řešení

```python
for package in package_list:
    if hasattr(package, 'value') and package.state == "nedoručen":
        total_value += package.value
```

---

# Datové třídy

## 1 - Balík jako datová třída ○○○♦♦

Uprav třídu `Package` na datovou třídu. Třída bude mít atributy `address`, `weight`, a `state`. U `state` nastav výchozí
hodnotu jako nedoručen. U každého z atributů vymysli a nastav vhodný datový typ. Existující metody ve třídě ponech.
Neměň ani třídu `ValuablePackage`.

Následně vyzkoušej, zda funguje vytváření balíků.

### Řešení

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
