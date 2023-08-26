## Zkušební doba ◇◆◆◆◆

U zaměstnanců budeme nově evidovat, jestli jsou ve zkušební době.

- Rozšiř metodu `__init__` třídy `Zamestnanec` o parametr `zkusebni_doba`, který bude typu `bool`. Tuto hodnotu ulož
  jako atribut třídy `Zamestnanec`.
- Uprav metodu `__str__`. Pokud je zaměstnanec ve zkušební době, přidej k jeho/jejímu výpisu text `Je ve zkušební době.`

<details>
<summary><b>Řešení</b></summary>


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

</details>
