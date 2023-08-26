## Kniha ◇◇◇◆◆

Zkus pro nakladatelství vytvořit software s využitím tříd a objektů. Vytvoř tedy třídu `Book`, která reprezentuje knihu.
Každá kniha bude mít atributy `title`, `pages` a `price`. Hodnoty nastav ve funkci `__init__`.

- Přidej knize funkci `get_info()`, která vypíše informace o knize v nějakém pěkném formátu.
- Přidej metodu `get_time_to_read()`. Metoda vrátí čas potřebný na přečtení knihy v hodinách. S využitím
  atributu `pages` vypočítej čas na přečtení knihy, přičemž uvažuj, že přečtení jedné stránky zabere průměrnému
  čtenáři/čtenářce 4 minuty.

<details>
<summary><b>Řešení</b></summary>


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

</details>
