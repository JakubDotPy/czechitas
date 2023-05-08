# Cvičení

## 1 - Balík ◇◇◆◆◆

Uvažuj, že navrhuješ software pro zásilkovou společnost.

- Vytvoř třídu `Balik`, která bude mít tři atributy - `adresa`, `hmotnost` a `doruceno`. První dva atributy nastav
  pomocí parametrů funkce `__init__`. Parametr `doruceno` nastav na začátku jako `False`.
- Připoj ke třídě funkci `doruc`, která změní hodnotu parametru `doruceno` na `True`.
- Přidej metodu `__str__()`, která vypíše `adresu`, `hmotnost` a informaci o tom, zda byl balík již doručen.
- Zkus si vytvořit nějaké objekty ze třídy Balik a ověř, že vše funguje.

### Řešení

```python
class Balik:
    def __init__(self, adresa, hmotnost):
        self.adresa = adresa
        self.hmotnost = hmotnost
        self.doruceno = False

    def doruc(self):
        self.doruceno = True

    def __str__(self):
        return f'Balik na adresu {self.adresa}, hmotnost {self.hmotnost}' \
               f' - {"doručen" if self.doruceno else "nedoručen"}'


b1 = Balik('Petr - Praha 10', 10)
print(b1)

b2 = Balik('Andrea - Plzeň', 20)
b2.doruc()
print(b2)
```

## 2 - Kniha ◇◇◇◆◆

Zkus pro našeho nakladatele vytvořit software s využitím tříd a objektů.  
Vytvoř tedy třídu `Kniha`, která reprezentuje knihu. Každá kniha bude mít atributy `nazev`, `pocet_stran` a `cena`.
Hodnoty nastav ve funkci `__init__`.

- Přidej knize funkci `__str()__`, která vypíše informace o knize v nějakém pěkném formátu.
- Občas se stane, že se kniha moc neprodává a knihkupec se snaží nalákat kupující slevou. Přidej metodu `sleva()`, která
  bude mít jeden parametr - velikost slevy v procentech. Funkce sníží cenu knihy o dané procento.

### Řešení

```python
class Kniha:
    def __init__(self, nazev, pocet_stran, cena):
        self.nazev = nazev
        self.pocet_stran = pocet_stran
        self.cena = cena

    def sleva(self, procent):
        self.cena *= 1 - (procent / 100)

    def __str__(self):
        return f'{self.nazev}, {self.pocet_stran} stran - {self.cena} Kč'


k = Kniha('Motýlek', 300, 100)
print(k)
k.sleva(20)
print(k)
```

## 3 - Zkušební doba

U zaměstnanců budeme nově evidovat, jestli jsou ve zkušební době.

```python
class Zamestnanec:
    def __init__(self, jmeno, pozice):
        self.jmeno = jmeno
        self.pozice = pozice

    def __str__(self):
        return f"{self.jmeno} pracuje na pozici {self.pozice}."
```

- Rozšiř metodu `__init__` třídy `Zamestnanec` o parametr `zkusebni_doba`, který bude typu `bool`. Tuto hodnotu ulož
  jako atribut třídy `Zamestnanec`.
- Uprav metodu `__str__()`. Pokud je zaměstnanec ve zkušební době, přidej k jeho/jejímu výpisu text `"Je ve zkušební
  době."`

### Řešení

```python
class Zamestnanec:
    def __init__(self, jmeno, pozice, zkusebni_doba):
        self.jmeno = jmeno
        self.pozice = pozice
        self.zkusebni_doba = zkusebni_doba

    def __str__(self):
        return f"{self.jmeno} pracuje na pozici {self.pozice}." \
               f"{' Je ve zkušební době.' if self.zkusebni_doba else ''}"


z1 = Zamestnanec('Karel', 'dělník', zkusebni_doba=False)
print(z1)

z2 = Zamestnanec('Josef', 'brigádník', zkusebni_doba=True)
print(z2)
```
