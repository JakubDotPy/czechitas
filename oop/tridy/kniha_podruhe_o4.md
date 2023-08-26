## Kniha podruhé ◇◆◆◆◆

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

<details>
<summary><b>Řešení</b></summary>


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

</details>
