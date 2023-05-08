# Cvičení: Dědičnost

Třídy z lekce které budeme rozšiřovat:

```python
class Zamestnanec:
    def __init__(self, jmeno, pozice):
        self.jmeno = jmeno
        self.pozice = pozice
        self.dovolena = 160

    def cerpej_dovolenou(self, pocet_hodin):
        if self.dovolena >= pocet_hodin:
            self.dovolena -= pocet_hodin
            return "Užij si to."
        else:
            return f"Máš nárok je na {self.dovolena} hodin."

    def __str__(self):
        return f"Zam. {self.jmeno} a pracuje na poz. {self.pozice}"


class Manazer(Zamestnanec):
    def __init__(self, jmeno, pozice, pocet_podrizenych):
        super().__init__(jmeno, pozice)
        self.pocet_podrizenych = pocet_podrizenych

    def __str__(self):
        return super().__str__() + f" - Počet podřízených: {self.pocet_podrizenych}"


# ------------------------------

class Balik:
    def __init__(self, adresa, hmotnost):
        self.adresa = adresa
        self.hmotnost = hmotnost
        self.dorucen = False

    def dorucit(self):
        self.dorucen = True

    def __str__(self):
        return f'Balik na adresu {self.adresa}, hmotnost {self.hmotnost}'\
               f' - {"doručen" if self.dorucen else "nedoručen"}'
```

## 1 - částečný úvazek ◇◇◆◆◆

Naše firma se rozhodla zaměstnávat i pracovníky na částečné úvazky, pro které bude vytvořena zvláštní třída. Vytvoř
novou třídu `Brigadnik`, která bude dědit od třídy `Zamestnanec` a bude mít navíc atribut `uvazek`, který reprezentuje
velikost úvazku oproti plnému. Přidej informaci o úvazku k výpisu informací do funkce `__str__()`.

### Řešení

```python
class Brigadnik(Zamestnanec):
    def __init__(self, jmeno, pozice, uvazek):
        super().__init__(jmeno, pozice)
        self.uvazek = uvazek

    def __str__(self):
        return super().__str__() + f' velikost uvazku: {self.uvazek}'
```

## 2 - Balík ◇◇◆◆◆

Pokračuj ve své práci pro zásilkovou společnost.  
Společnost nově doručuje i cenné balíky, které mají zadanou určitou hodnotu. Vytvoř třídu `CennyBalik`, která dědí od
třídy `Balik`. `CennyBalik` má navíc atribut `hodnota`, ostatní atributy dědí od třídy `Balik`. Atribut `hodnota` nastav
pomocí funkce `__init__`. Ostatní parametry předej funkci `__init__` třídy `Balik`. Vytvoř si alespoň jeden objekt a
zkus volání jeho funkcí.

### Řešení

```python
class CennyBalik(Balik):
    def __init__(self, adresa, hmotnost, hodnota):
        super().__init__(adresa, hmotnost)
        self.hodnota = hodnota

    def __str__(self):
        return super().__str__() + f' - hodnota: {self.hodnota}'


b1 = CennyBalik('Pepa - Praha 10', 10, 200)
b1.dorucit()
print(b1)
```

# Kombinace seznamu a objektů

## 1 - Řidič ◇◆◆◆◆

Pokračuj ve své práci pro zásilkovou společnost. Společnost nyní eviduje jednotlivé řidiče a eviduje balíky, které má každý řidič doručit.

- Vytvoř třídu `Ridic`, která má dva atributy: `jmeno` (jméno řidiče) a `seznam_baliku` (seznam balíků k doručení, na začátku je prázdný).
- Přidej třídě metodu `prirad_balik`, která bude mít jeden parametr - `balik` (balík k doručení, může se jednat i o cenný balík). Funkce nejprve zkontroluje, zda balík již nebyl doručen. Pokud ano, vypíše funkce text: `"Nelze přiřadit, balík již byl doručen."` Pokud balík ještě nebyl doručen, je přidán do seznamu balíků `seznam_baliku` (použij funkci `append`).
- U řidiče chceme sledovat, kolik by měl ještě doručit balíků. Napiš funkci `zbyva_baliku`, která vrátí počet balíků, které má řidič přiřazené a ještě je nedoručil.

### Řešení

```python
class Ridic:

    def __init__(self, jmeno):
        self.jmeno = jmeno
        self.seznam_baliku = [] 

    def prirad_balik(self, balik):
        if balik.dorucen:
            print('Nelze přiřadit, balík již byl doručen.')
        else:
            self.seznam_baliku.append(balik)

    def zbyva_baliku(self):
        return len(self.seznam_baliku)
```
