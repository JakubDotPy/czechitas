# Cvičení: Čtení ze souborů

## 1 - Výplata přesněji ○○○♦♦

Zatím jsme výplatu počítali za předpokladu, že každý měsíc odpracujeme stejný počet hodin, což není příliš realistické.  
Vytvořte proto textový soubor `vykaz.txt`, který bude obsahovat 12 řádků a na každém řádku počet odpracovaných hodin za každý měsíc za poslední rok.

- Otevřete tento soubor ve svém programu a načtěte hodnoty na řádcích do seznamu `vykaz`. Vytiskněte tento seznam do terminálu funkcí `print()` abyste si ověřili, že jste soubor načetli správně.
- Nechte uživatele zadat na příkazovém řádku hodinovou mzdu. Spočítejte a na výstup vytiskněte celkovou výplatu za celý rok a průměrnou výplatu na jeden měsíc.

### Řešení

```python
import statistics

with open('vykaz.txt') as file:
    vykaz = []
    for hodnota in file:
        vykaz.append(int(hodnota))

print(vykaz)

hodinovka = int(input('Zadej hodinovou mzdu: '))

vyplaty = []
for pocet_hodin in vykaz:
    vyplaty.append(pocet_hodin * hodinovka)
    
print(f'Vyplata za cely rok je {sum(vyplaty)}, průměrná {statistics.mean(vyplaty)}')
```

## 2 - Počet slov ○○♦♦♦

Stáhněte si odevzdanou slohovou práci.  
Zadání bylo sepsat text o nejméně 150ti slovech pojednávající o našem hlavním městě.  
Napište program, který spočítá počet slov v tomto textu, abychom věděli, zda bylo zadání formálně splněno. Nechte se vést následujícím návodem.

- Nechte váš program otevřít soubor a načíst jednotlivé řádky do seznamu
- Každý řádek převeďte na seznam slov. Slovem se rozumí vše, co je odděleno mezerou nebo novým řádkem
- Vypište na výstup počty slov na každém řádku
- Vypište na výstup celkový počet všech slov v souboru

### Řešení

```python
seznam_radku = []
with open(r'slohovka.txt', encoding='utf-8') as file:
    for radek in file:
        seznam_radku.append(radek.split())  # pridame rovnou rozsekany radek

celkovy_pocet_slov = 0
print('pocty radku')
for radek in seznam_radku:
    pocet_slov_v_radku = len(radek)
    print(pocet_slov_v_radku)
    celkovy_pocet_slov += pocet_slov_v_radku

print(f'celkovy pocet slov je {celkovy_pocet_slov}')
```

# Bonus

## 3 - Půjčovna ○♦♦♦♦

Půjčovna aut má v každém kraji ČR jedno auto s danou SPZ. Ke konci roku chce zjistit, kolik všechna auta najezdila dohromady kilometrů. V souboru auta.txt je pro každou SPZ zaznamenáno kolik dané auto ujelo kilometrů za daný rok. Hodnoty jsou v tisících kilometrů. Bohužel se v jednotlivých krajích blbě zkoordinovali a někdo používal desetinnou čárku, někdo zase tečku.

**Pozor!** V souboru s daty je ještě jeden problém, který není na první pohled vidět!

Napište program, který na výstup vypíše součet všech ujetých kilometrů. Jistě se vám bude hodit metoda řetězců jménem `replace()`.

### Řešení

```python
ujete_kilometry = 0
with open(r'auta.txt', encoding='utf-8') as file:
    for radek in file:
        kilometry = float(radek.replace(',', '.').split(' ')[-1])
        ujete_kilometry += kilometry

print(f'celkovy pocet ujetych kilometru je {ujete_kilometry}')
```

---

# Cvičení: Zápis do souborů

## 1 - Dny v měsíci ○○○○♦

Napište program, který bude mít přímo v kódu zapsaný počet dní v jednotlivých měsících takto:

```python
pocty_dni = [31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31]
```

Nechte váš program vypsat tento seznam do souboru s názvem `kalendar.txt`, každé číslo na jeden řádek.

### Řešení

```python
pocty_dni_text = []
for pocet_dni in pocty_dni:
    pocty_dni_text.append(str(pocet_dni))

with open('kalendar.txt', 'w', encoding='utf-8') as output_file:
    for dny in pocty_dni_text:
        print(dny, file=output_file)
```

## 2 - Vytvoření souboru ○○○♦♦

Napište program, který se po spuštění zeptá na název souboru, který má vytvořit (nebo přepsat, pokud už ten soubor existuje), a pak se zeptá na řádek textu, který má do souboru zapsat.

### Řešení

```python
jmeno_souboru = input('Zadej nazev souboru: ')
radek = input('co chceš zapsat?: ')

with open(jmeno_souboru, 'w', encoding='utf-8') as f:
    f.write(radek)
```

## 3 - Rozepsaná výplata ○○♦♦♦

Modifikujte program pro počítání výplaty z předchozí sekce tak, aby nevypisoval průměrnou výplatu za rok, nýbrž aby vypsal konkrétní vyplacenou částku pro každý měsíc zvlášť.

- Nejprve tyto informace vypište na terminál
- Poté program upravte tak, aby vypsal tyto výsledky do souboru

### Řešení

```python
hodinovka = int(input('Zadej hodinovou mzdu: '))

# muzeme si otevrit oba soubory zaroven
with open('vykaz.txt') as vstupni_soubor:
    with open('vystup.txt', 'w') as vystup:
        for hodnota in vstupni_soubor:
            print(int(hodnota) * hodinovka, file=vystup)
```

---

# Doporučené úložky na doma

## 1 - Přeznámkování ○○○♦♦

Univerzita pro celoživotní vzdělávání se rozhodla změnit svůj známkovací systém z číselných známek 1 až 5 na hodnocení písmeny A až F. Bohužel změna se odehrála jaksi uprostřed semestru, takže je potřeba změnit aktuální výkazy o známkách z čísel na písmena. Nechte se vést následujícím postupem.

- Otevřete si dokument s jedním výkazem známek.
- Zkopírujte si tuto tabulku do textového souboru.
- Napište program, který tuto tabulku načte ze souboru a změní všechny známky tak, že 1 bude A, 2 bude B, 3 bude C, 4 bude D a 5 bude F.
- Vypište váš výsledek do nějakého souboru tak, aby se z něj dal zase zkopírovat do tabulky Google.
- Vytvořte novou Google tabulku, která vypadá stejně jako ta výše avšak s převedenými známkami.

### Řešení

```python
with open('puvodni_tabulka.txt', encoding='utf-8') as vstup:
    text = vstup.read()

# pokud uzavreme cast kodu do zavorek, muzeme pak rozdelit na jednotlive radky
novy_text = (
    text
    .replace('1', 'A')
    .replace('2', 'B')
    .replace('3', 'C')
    .replace('4', 'D')
    .replace('5', 'E')
)

with open('nova_tabulka.txt', 'w') as vystup:
    vystup.write(novy_text)
```

## 2 - Pasažéři ○♦♦♦♦

Autobus mezi Zdebudevsí a Kozoprdy jezdí čtyřikrát denně každý všední den v týdnu. Za poslední týden jsme naměřili počty pasažérů pro každou jízdu tam i zpět. Data jsou uložená v souboru pasazeri.txt. Jízda vždy obsahuje dvě čísla oddělená čárkou, která udávají počet pasažérů směrem tam a směrem zpět.

- Napište program, který pro první den vypíše, kolik pasažérů jelo celkem směrem tam a kolik směrem zpět.
- Nechť váš program vypisuje součty pasažérů ze celý týden, tedy kolik lidí za celý týden jelo směrem tam a kolik směrem zpět.

### Řešení

```python
cesty = {}

with open('pasazeri.txt', encoding='utf-8') as vstup:
    cislo_dne = 0
    for radek in vstup:
        den = {
            'tam' : [],
            'zpet': [],
        }
        for tam_zpatky in radek.split():
            tam_zpatky = tam_zpatky.split(',')
            den['tam'].append(int(tam_zpatky[0]))
            den['zpet'].append(int(tam_zpatky[1]))
        cesty[cislo_dne] = den
        cislo_dne += 1

print(f'prvni den tam: {sum(cesty[0]["tam"])}')
print(f'prvni den zpet: {sum(cesty[0]["zpet"])}')

celkem_tam = 0
celkem_zpet = 0
for den, data in cesty.items():
    celkem_tam += sum(data['tam'])
    celkem_zpet += sum(data['zpet'])

print(f'celkem jelo {celkem_tam} lidi tam a {celkem_zpet} lidi zpet')
```

---

# Volitelné úložky na doma

## 3 - Karty 1 ○○○○♦

Napište program, který vylosuje náhodnou hrací kartu z klasické whistové sady obsahující 52 karet, rozdělených do čtyř barev (kříže, srdce, piky, káry), s hodnotami 2, 3, 4, 5, 6, 7, 8, 9, 10, J (kluk), Q (dáma), K (král), A (eso).

Výstup programu může vypadat například takto:

```text
Karta: kluk kříže
```

### Řešení

```python
import random

hodnoty = list(range(2, 11)) + ['J', 'Q', 'K', 'A']
barvy = ['kříže', 'srdce', 'piky', 'káry']

print(f'Karta: {random.choice(hodnoty)} {random.choice(barvy)}')
```

## 4 - Karty 2 ○○○♦♦

Napište program, který vylosuje seznam 4 náhodných hracích karet podobně jako v předchozím úkolu. Můžeme si představovat, že rozdáváme karty například v pokeru. Zatím pro jednoduchost nebudeme řešit, že se nám může nějaká karta v seznamu opakovat.

- Vymyslete, jak budete vylosovanou kartu v seznamu reprezentovat. Vypište pak tento seznam na výstup.
- Dále k tomuto seznamu vypište součet hodnot všech vylosovaných karet. Položme hodnotu karet J, Q a K rovnu deseti a eso rovnu jedné.

### Řešení

```python
import random

hodnoty = list(range(2, 11)) + ['J', 'Q', 'K', 'A']
body = list(range(2, 11)) + [10, 10, 10, 1]
barvy = ['kříže', 'srdce', 'piky', 'káry']

karty = []
for index in range(13):  # cislo karty
    for barva in barvy:
        # kartu nam reprezejntuje trojice (body, hodnota, barva)
        # napr.: (10, 'J', 'srdce')
        karta = (body[index], hodnoty[index], barva)
        karty.append(karta)

ruka = random.sample(karty, 4)
print(f'vylosovano {ruka}')

body = 0
for karta in ruka:
    body += karta[0]
    
print(f'mame celkem {body}')
```

## 5 - Karty3 ○♦♦♦♦

Zkusme vyřešit problém losování karet tak, aby se nám nemohlo stát, že nám nějaká karta padne vícekrát, když by správně v balíčku měla být od každé karty pouze jedna.

Ze souboru karty.txt si načtěte do seznamu kompletní balíček karet. Zadání je stejné jako v předchozí úložce, tedy vylosovat 4 karty z balíčku a vypsat je jako seznam spolu se součtem hodnot.

Existuje vícero možných postupů, které vedou ke stejnému výsledku. Zde už můžete trochu zagooglit. Ve většině postupů se vám bude hodit metoda, který umí odstranit prvek seznamu na zadaném indexu:

```python
x = [1, 2, 3]
x.pop(0)
print(x)  # [2, 3]
```

Také se vám může hodit funkce `shuffle()` z modulu `random`, která umí náhodně zamíchat seznam.

### Řešení

Použijeme kod z předchozího příkladu a zaměříme se na vygenerovaný seznam karet.

```python
# zamichame
random.shuffle(karty)

# ctyrykrat si do ruky vezmeme posledni kartu ze seznamu
# seznam karet se ted zmensuje a muzeme tak opakovat pro vice hracu

ruka = []
for _ in range(4):
    ruka.append(karty.pop())
```