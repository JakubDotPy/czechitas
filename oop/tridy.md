# Cvičení: Objekty a třídy

## 1 - Balík ◇◇◆◆◆

Uvažuj, že navrhuješ software pro zásilkovou společnost.

- Vytvoř třídu `Package`, která bude mít tři atributy - `address`, `weight` a `state`. Vytvoř metodu `__init__`, která
  uloží hodnoty parametrů metody do atributů.
- Přidej metodu `get_info()`, která vrátí informace o balíku jako řetězec. Uvažuj například větu "Balík na adresu
  Václavské Náměstí 12, Praha má hmotnost 0.25 kg je je ve stavu nedoručen".
- Zkus si vytvořit alespoň dva objekty ze třídy `Balik`. U `address` uvažujeme typ řetězec (`str`), u `weight` desetinné
  číslo. U atributu `state` zadávej pro zjednodušení pouze dva stavy: `doručen` a `nedoručen`.
- Vypiš informace, které generuje metoda `get_info()`, na obrazovku, a ověř, že je vše v pořádku.

### Řešení

```python
class Package:
    def __init__(self, address, weight, state):
        self.address = address
        self.weight = weight
        self.state = state

    def get_info(self):
        return f"Balík na adresu {self.address} má hmotnost {self.weight} kg a je ve stavu {self.state}."


# Vytvoření objektů
package1 = Package("Václavské Náměstí 12, Praha", 0.25, "nedoručen")
package2 = Package("Jiřího z Poděbrad 9, Brno", 1.5, "doručen")

# Výpis informací o balících
print(package1.get_info())
print(package2.get_info())
```

## 2 - Kniha ◇◇◇◆◆

Zkus pro nakladatelství vytvořit software s využitím tříd a objektů. Vytvoř tedy třídu `Book`, která reprezentuje knihu.
Každá kniha bude mít atributy `title`, `pages` a `price`. Hodnoty nastav ve funkci `__init__`.

- Přidej knize funkci `get_info()`, která vypíše informace o knize v nějakém pěkném formátu.
- Přidej metodu `get_time_to_read()`. Metoda vrátí čas potřebný na přečtení knihy v hodinách. S využitím
  atributu `pages` vypočítej čas na přečtení knihy, přičemž uvažuj, že přečtení jedné stránky zabere průměrnému
  čtenáři/čtenářce 4 minuty.

### Řešení

```python
class Book:
    def __init__(self, title, pages, price):
        self.title = title
        self.pages = pages
        self.price = price

    def get_info(self):
        return f"Kniha '{self.title}' má {self.pages} stran a stojí {self.price} Kč."

    def get_time_to_read(self):
        time_to_read_in_minutes = self.pages * 4  # strana za 4 minuty
        time_to_read_in_hours = time_to_read_in_minutes / 60
        return time_to_read_in_hours


# Vytvoření objektů
book1 = Book("Problém tří těles", 447, 250)
book2 = Book("Temný les", 600, 300)

# Výpis informací o knihách a času potřebného na jejich přečtení
print(book1.get_info())
print(f"Čas potřebný na přečtení: {book1.get_time_to_read()} hodin")
print(book2.get_info())
print(f"Čas potřebný na přečtení: {book2.get_time_to_read()} hodin")
```

---

# Cvičení: Další metody

## 1 - Balík podruhé ○○♦♦♦

Vrať se k návrhu software pro zásilkovou společnost.

- U třídy `Package` přejmenuj metodu `get_info()` na `__str__()` a vyzkoušej, jestli nyní stačí k získání informací o
  balíku funkce `print()`.
- Přidej metodu `deliver()`. Půjde o obdobu tlačítka, které řidič nebo řidička zmáčkne při doručení balíku a zaznamená
  tak jeho doručení. Metoda nejprve zkontroluje, zda balík náhodou již není ve stavu `doručen`. Pokud ano, metoda vrátí
  zprávu "Balík již byl doručen". Tím bude řidič (řidička) informován(a) o tom, že se pravděpodobně spletl(a) a snaží se
  zaznamenat doručení u špatného balíku. Pokud balík není ve stavu `doručen`, změň jeho stav právě na `doručen` a vrať
  zprávu "Doručení uloženo".
- Vyzkoušej metodu `deliver()`. Co se stane, pokud ji u jednoho balíku zavoláš dvakrát?

### Řešení

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

---

# Bonusy

## 2 - Kniha podruhé ○♦♦♦♦

Vrať se k práci se třídou `Book`. Pokud jsi ji nestihl(a) v minulé části vytvořit, vrať se nejprve k zadání příkladu na
předchozí stránce a třídu si vytvoř.

- U knihy budeme chtít evidovat, kolik kusů bylo prodáno. Přidej atribut `sold`, jehož hodnotu bude možné nastavit v
  metodě `__init__()`. Dále přidej atribut `costs`, které představují náklady na jednu knihu (např. tisk, doprava do
  knihkupectví, podíl autora (autorky) atd.).
- Přidej metodu `profit()`, která vrátí celkový zisk z knihy. Zisk vypočti na základě vzorce: prodané kusy * (cena -
  náklady).
- Přidej metodu `rating()`, která vrátí hodnocení knihy na základě jejího zisku. Pokud bude zisk méně než 50 tisíc, vrať
  hodnotu "propadák". Pokud bude zisk mezi 50 tisíc a 500 tisíc, vrať hodnotu "průměr". Pokud bude vyšší než 500 tisíc,
  vrať hodnotu "úspěch".

### Řešení

```python
class Book:
    def __init__(self, title, pages, price, sold, costs):
        self.title = title
        self.pages = pages
        self.price = price
        self.sold = sold
        self.costs = costs

    def get_info(self):
        return f"Kniha '{self.title}' má {self.pages} stran, stojí {self.price} Kč, bylo prodáno {self.sold} kusů a náklady na jednu knihu činí {self.costs} Kč."

    def get_time_to_read(self):
        return self.pages * 4 / 60

    def profit(self):
        return self.sold * (self.price - self.costs)

    def rating(self):
        profit = self.profit()
        if profit < 50000:
            return "propadák"
        elif profit <= 500000:
            return "průměr"
        else:
            return "úspěch"


# Vytvoření objektů
book1 = Book("Problém tří těles", 447, 250)
book2 = Book("Temný les", 600, 300)

# Výpis informací o knihách, zisku a hodnocení
print(book1.get_info())
print(f"Zisk: {book1.profit()} Kč, Hodnocení: {book1.rating()}")
print(book2.get_info())
print(f"Zisk: {book2.profit()} Kč, Hodnocení: {book2.rating()}")
```

## 3 - Zkušební doba ○♦♦♦♦

U zaměstnanců budeme nově evidovat, jestli jsou ve zkušební době.

- Rozšiř metodu `__init__` třídy `Zamestnanec` o parametr `zkusebni_doba`, který bude typu `bool`. Tuto hodnotu ulož
  jako atribut třídy `Zamestnanec`.
- Uprav metodu `__str__`. Pokud je zaměstnanec ve zkušební době, přidej k jeho/jejímu výpisu text `Je ve zkušební době.`

### Řešení

```python
class Employee:
    def __init__(self, name, position, holiday_entitlement, probation_period):
        self.name = name
        self.position = position
        self.holiday_entitlement = holiday_entitlement
        self.probation_period = probation_period

    def __str__(self):
        text = f"Zaměstnanec {self.name} pracuje na pozici {self.position}."
        if self.probation_period:
            text = text + " Je ve zkušební době."
        return text

    def take_holiday(self, days):
        if self.holiday_entitlement >= days:
            self.holiday_entitlement -= days
            return "Užij si to."
        else:
            return f"Bohužel už máš nárok jen na {self.holiday_entitlement} dní."


# Vytvoření objektů
employee1 = Employee("Jan Novák", "Programátor", 25, True)
employee2 = Employee("Marie Kovaříková", "HR Manager", 30, False)

# Výpis informací o zaměstnancích
print(employee1)
print(employee2)
```

---

# Čtení na doma

## 1 - Balík potřetí ○○○○♦

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
