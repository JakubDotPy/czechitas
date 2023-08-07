# Cvičení: Objekty a třídy

## 1 - Balík ◇◇◆◆◆

Uvažuj, že navrhuješ software pro zásilkovou společnost.

- Vytvoř třídu `Package`, která bude mít tři atributy - `address`, `weight` a `state`. Vytvoř metodu `__init__`, která
  uloží hodnoty parametrů metody do atributů.
- Přidej metodu `get_info()`, která vrátí informace o balíku jako řetězec. Uvažuj například větu 'Balík na adresu
  Václavské Náměstí 12, Praha má hmotnost 0.25 kg je ve stavu nedoručen'.
- Zkus si vytvořit alespoň dva objekty ze třídy `Package`. U `address` uvažujeme typ řetězec (`str`), u `weight`
  desetinné číslo. U atributu `state` zadávej pro zjednodušení pouze dva stavy: `doručen` a `nedoručen`.
  Vypiš informace, které generuje metoda get_info(), na obrazovku, a ověř, že je vše v pořádku.

### Řešení

```python
class Package:
    def __init__(self, address, weight, state):
        self.address = address
        self.weight = weight
        self.state = state

    def get_info(self):
        return f'Balik na adresu {self.address}, má hmotnost {self.weight} kg je ve stavu {self.state}.'


b1 = Package('Petr - Praha 10', 10, 'doručen')
print(b1.get_info())

b2 = Package('Andrea - Plzeň', 20, 'nedoručen')
print(b2.get_info())
```

## 2 - Kniha ◇◇◇◆◆

Zkus pro nakladatelství vytvořit software s využitím tříd a objektů. Vytvoř tedy třídu `Book`, která reprezentuje knihu.
Každá kniha bude mít atributy `title`, `pages` a `price`. Hodnoty nastav ve funkci `__init__`.

- Přidej knize funkci `get_info()`, která vypíše informace o knize v nějakém pěkném formátu.
- Přidej metodu `get_time_to_read()`. Metoda vrátí čas potřebný na přečtení knihy v hodinách. S využitím
  atributu `pages`
  vypočítej čas na přečtení knihy, přičemž uvažuj, že přečtení jedné stránky zabere průměrnému čtenáři/čtenářce 4
  minuty.

### Řešení

```python
class Book:
    def __init__(self, title, pages, price):
        self.title = title
        self.pages = pages
        self.price = price

    def get_info(self):
        return f'Kniha: {self.title}\nPočet stran: {self.pages}\nCena: {self.price} CZK'

    def get_time_to_read(self):
        time_to_read_in_minutes = self.pages * 4  # strana za 4 minuty
        time_to_read_in_hours = time_to_read_in_minutes / 60
        return time_to_read_in_hours


# Příklad použití:
book1 = Book('Harry Potter a Kámen mudrců', 336, 250)
print(book1.get_info())
print(f'Čas na přečtení: {book1.get_time_to_read()} hodin')
```

# Cvičení: Další metody

## 1 - Balík podruhé ○○♦♦♦

Vrať se k návrhu software pro zásilkovou společnost.

- U třídy `Package` přejmenuj metodu `get_info()` na `__str__()` a vyzkoušej, jestli nyní stačí k získání informací o
  balíku funkce `print()`.
- Přidej metodu `deliver()`. Půjde o obdobu tlačítka, které řidič nebo řidička zmáčkne při doručení balíku a zaznamená
  tak jeho doručení. Metoda nejprve zkontroluje, zda balík náhodou již není ve stavu `doručen`. Pokud ano, metoda vrátí
  zprávu 'Balík již byl doručen'. Tím bude řidič (řidička) informován(a) o tom, že se pravděpodobně spletl(a) a snaží se
  zaznamenat doručení u špatného balíku. Pokud balík není ve stavu `doručen`, změň jeho stav právě na `doručen` a vrať
  zprávu 'Doručení uloženo'.
- Vyzkoušej metodu `deliver()`. Co se stane, pokud ji u jednoho balíku zavoláš dvakrát?

### Řešení

```python
class Package:
    def __init__(self, address, weight, state):
        self.address = address
        self.weight = weight
        self.state = state

    def __str__(self):
        return f'Balik na adresu {self.address}, má hmotnost {self.weight} kg je ve stavu {self.state}.'

    def deliver(self):
        if self.state == 'doručen':
            return 'Balík již byl doručen'
        else:
            self.state = 'doručen'
            return 'Doručení uloženo'


package1 = Package('Andrea - Plzeň', 20, 'nedoručen')
print(package1)
print(package1.deliver())
print(package1)

print(package1.deliver())
```

---

# Bonusy

## 2 - Kniha podruhé ○♦♦♦♦

Vrať se k práci se třídou `Book`. Pokud jsi ji nestihl(a) v minulé části vytvořit, vrať se nejprve k zadání příkladu na
předchozí stránce a třídu si vytvoř.

- U knihy budeme chtít evidovat, kolik kusů bylo prodáno. Přidej atribut `sold`, jehož hodnotu bude možné nastavit v
  metodě `__init__()`. Dále přidej atribut `costs`, které představují náklady na jednu knihu (např. tisk, doprava do
  knihkupectví, podíl autora(autorky) atd.).
- Přidej metodu `profit()`, která vrátí celkový zisk z knihy. Zisk vypočti na základě vzorce: prodané kusy * (cena -
  náklady).
- Přidej metodu `rating()`, která vrátí hodnocení knihy na základě jejího zisku. Pokud bude zisk méně než 50 tisíc, vrať
  hodnotu 'propadák'. Pokud bude zisk mezi 50 tisíc a 500 tisíc, vrať hodnotu 'průměr'. Pokud bude vyšší než 500 tisíc,
  vrať hodnotu 'úspěch'.

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
        return f'Kniha: {self.title}\nPočet stran: {self.pages}\nCena: {self.price} CZK'

    def get_time_to_read(self):
        time_to_read_in_minutes = self.pages * 4  # strana za 4 minuty
        time_to_read_in_hours = time_to_read_in_minutes / 60
        return time_to_read_in_hours

    def profit(self):
        return self.sold * (self.price - self.costs)

    def rating(self):
        book_profit = self.profit()
        if book_profit < 50000:
            return 'propadák'
        elif 50000 <= book_profit < 500000:
            return 'průměr'
        else:
            return 'úspěch'


# Příklad použití:
book1 = Book('Harry Potter a Kámen mudrců', 336, 250, 1000, 100)
print(book1.get_info())
print(f'Čas na přečtení: {book1.get_time_to_read()} hodin')
print(f'Profit: {book1.profit()}')
print(f'Rating: {book1.rating()}')
```

## 3 - Zkušební doba ○♦♦♦♦

U zaměstnanců budeme nově evidovat, jestli jsou ve zkušební době.

- Rozšiř metodu `__init__` třídy `Employee` o parametr `probation_period`. Tuto hodnotu ulož jako atribut
  třídy `Employee`.
- Uprav metodu `__str__`. Pokud je zaměstnanec ve zkušební době, přidej k jeho/jejímu výpisu text "Je ve zkušební době".

### Řešení

```python
class Employee:
    def __init__(self, name, position, holiday_entitlement, probation_period):
        self.name = name
        self.position = position
        self.holiday_entitlement = holiday_entitlement
        self.probation_period = probation_period

    def __str__(self):
        text = f'Zaměstnanec {self.name} pracuje na pozici {self.position}.'
        prob_text = 'Je ve zkušební době.'
        if self.probation_period:
            text = f'{text} {prob_text}'
        return text


frantisek = Employee("František Novák", "konstruktér", 25, True)
print(frantisek)
```

---

# Čtení na doma

## 1 - Balík potřetí ○○○○♦

Vrať se k návrhu software pro zásilkovou společnost. U třídy `Package` uprav atribut `state` tak, aby byl chráněný.
Ověř, že vytváření objektů i výpisy informací o něm fungují.

### Řešení

```python
class Package:
    def __init__(self, address, weight, state):
        self.address = address
        self.weight = weight
        self._state = state

    def __str__(self):
        return f'Balik na adresu {self.address}, má hmotnost {self.weight} kg je ve stavu {self._state}.'

    def deliver(self):
        if self._state == 'doručen':
            return 'Balík již byl doručen'
        else:
            self._state = 'doručen'
            return 'Doručení uloženo'
```
