# Cvičení

## 1 - Jednoduché podmínky ◇◇◇◆◆

- Založte si program `prihlaseni.py`. V tomto nechte uživatele zadat svoje uživatelské jméno a poté heslo.
  Pokud se heslo neshoduje s heslem `'simsalabim'`, vypište na výstup `Vstup nepovolen` a zavolejte funkci `exit()`,
  aby uživatel neznalý hesla nemohl s programem dál pracovat.

- Na konec programu vlož příkaz, který se uživatele zeptá na věk. Pokud je uživatel starší 18 let, vypište na výstup
  `Smíš vstoupit` Pokud je mladší, vypiš `Vstup povolen od 18 let`.

### Řešení

```python
# prihlaseni.py

uzivatel = input('Zadej uživatelské jméno: ')
heslo = input('Zadej heslo: ')

if heslo != 'simsalabim':
    print('Vstup nepovolen!')
    exit()

vek = int(input('Zadej věk: '))
if vek >= 18:
    print('Smíš vstoupit.')
else:
    print('Vstup nepovolen!')
```

## 2 - Cena vstupenky ◇◇◇◆◆

A nyní opět pokračujeme v našem rezervačním systému.

- Program `vstupenky_01.py`, který jste napsali v předchozí fázi, si uložte jako `vstupenky_02.py`, abychom ho mohli
  dále rozšířit o výpočet ceny vstupenky.
- Jakmile máte v programu načtený věk uživatele, vytvořte si proměnnou `plna_cena`, do které uložte hodnotu 12.
- Vytvořte podmínku, která do proměnné `cena` uloží cenu spočítanou podle věku uživatele dle následujících pravidel
  - 0 euro pro návštěvníky mladší 6 let
  - 65% ze základní ceny pro návštěvníky 6 až 26 let (žák, student)
  - 100% ze základní ceny pro návštěvníky 27 až 64 let (dospělý)
  - 50% ze základní ceny pro ostatní (senior).  

Nezapomeňte na zaokrouhlování, ať nám cena vyjde v celých centech.
- Nakonec spočtenou cenu vypište s nějakou hezkou zprávou na výstup.

### Řešení

```python
# vstupenka_02.py

print('Divadlo Pěst na oko')
print('Vítejte v online rezervaci vstupenek')
print('Pro vstup do systému je potřeba registrace')

uzivatel = input('Zadej uživatelské jméno: ')
vek = int(input('Zadej věk: '))

plna_cena = 12
if vek < 6:
    cena = 0
elif vek <= 26:
    cena = plna_cena * 0.65
elif vek <= 64:
    cena = plna_cena
else:
    cena = plna_cena * 0.5

print(f'Cena vstupenky je {round(cena, 2)}.')
```

---

# Bonusy

## 3 - Registrace ◇◇◇◆◆

Založte si program `registrace.py`. Program nechá uživatele, aby si zvolil uživatelské jméno a heslo. Heslo jej nechejte
zadat dvakrát a ověřte, že jej uživatel zadal dvakrát stejně. V opačném případě vypište varování, že hesla nejsou
stejná. Při prvním zadávání ověřte, že heslo je bezpečné, což v tomto případě znamená, že je delší než 8 znaků.

### Řešení

```python
# registrace.py
uzivatel = input('Zadej uživatelské jméno: ')

heslo = input('Zadej heslo: ')
if len(heslo) <= 8:
    print('Heslo je příliš krátké')
    exit()

heslo_2 = input('Zadej heslo znovu: ')
if heslo != heslo_2:
  print('Hesla se neshodují.')
```

## 4 - Přestupný rok ◇◇◆◆◆

Napište program, který po zadání kalendářního roku vypíše, zda jde o rok přestupný, či nikoliv. Letopočet je přestupný,
pokud je dělitelný čtyřmi. Roky, které jsou dělitelné 100 jsou ovšem přestupné pouze tehdy, jsou-li zároveň dělitelné

400.

### Řešení

```python
rok = int(input("Zadej rok: "))

delitelne_4 = rok % 4 == 0
delitelne_100 = rok % 100 == 0
delitelne_400 = rok % 400 == 0

if delitelne_400 or (delitelne_4 and not delitelne_100):
  print("Rok je přestupný.")
else:
  print("Rok není přestupný")
```

---

# Čtení na doma

## 1 - Dělitelnost více čísly ◇◇◇◆◆

Požádejme uživatele, ať zadá celé číslo. Napiš program který zjistí, zda je číslo dělitelné 3 i 4 současně.

Tip: nezapomeňte si zadané číslo převést na int. Tip 2: K ověření dědičnosti použij operátor % - zbytek po celočíselném
dělení a zkontroluj, zda je výsledek 0. Například 15 % 5 vrací 0, protože 15 je dělitelné 5.

### Řešení

```python
cislo = int(input('Zadej celé číslo: '))

delitelne_3 = cislo % 3 == 0
delitelne_4 = cislo % 4 == 0

if delitelne_3 and delitelne_4:
  print('je delitelne 3 i 4')
else:
  print('neni delitelne 3 i 4 soucasne')
```

## 2 - Gymnázium ◇◇◇◆◆

Matematické gymnázium nabízí aplikaci, která sděluje informaci o povinnosti vykonání přijímací zkoušky.  
Požádejte uživatele o zadání známky z matematiky a průměru všech známek na posledním vysvědčení.  
Pokud má zájemce průměr známek nižší než 1.8 a z matematiky nejhůře dvojku, vypište
text: `"Přijmeme vás bez přijímací zkoušky."`.
V opačném případě vypište `"Musíte splnit přijímací zkoušku."`.

### Řešení

```python
matematika_znamka = int(input('Zadej známku z matematiky: '))
prumer_vysvedceni = float(input('Zadej průměr z vysvědčení: '))

if prumer_vysvedceni < 1.8 and matematika_znamka <= 2:
  print('Přijmeme vás bez přijímací zkoušky.')
else:
  print('Musíte splnit přijímací zkoušku.')
```

## 3 - Gymnázium ◇◇◆◆◆

Modifikujme si předchozí příklad. Horší známku z matematiky může student kompenzovat tím, že uspěje v matematické
olympiádě.  
Přidejte tedy dotaz, zda se uchazeč zúčastnil okresního kola matematické olympiády. Pokud ano, bude mu zkouška
odpuštěna, i kdyby jeho známka z matematiky byla horší. Požadavek na celkový průměr známek je však třeba stále dodržet.

Otázka může vypadat například takto:  
`input("Zúčastnil ses okresního kola krajské olympiády? [a/n] ")`

Pokud se student olympiády zúčastnil, odpoví `a`.

### Řešení

```python
matematika_znamka = int(input('Zadej známku z matematiky: '))
prumer_vysvedceni = float(input('Zadej průměr z vysvědčení: '))
olympiada = input("Zúčastnil ses okresního kola krajské olympiády? [a/n] ")

if prumer_vysvedceni < 1.8 and (matematika_znamka <= 2 or olympiada == 'a'):
  print('Přijmeme vás bez přijímací zkoušky.')
else:
  print('Musíte splnit přijímací zkoušku.')
```

---

# Bonusy

## 4 - Ruleta ◇◆◆◆◆

Na obrázku vidíte rozložení čísel na klasické Francouzské ruletě. Ruleta obsahuje čísla `0 - 36`. Každé číslo s výjimkou
nuly je buď sudé nebo liché a zároveň červené nebo černé. Pro čísla 1 až 10 a 19 až 28 platí, že lichá čísla jsou
červená a sudá jsou černá. Pro zbytek platí obrácené pravidlo, tedy lichá jsou černá a sudá červená. Nula není ani lichá
ani sudá, ani černá ani červená.

![Ruleta](https://kodim.cz/cms/assets/kurzy/uvod-do-progr-1/prvni-krucky/podminky/cteni-na-doma/excs%3Eruleta/roulette.png)

Napište program, kterému uživatel zadá číslo a program odpoví jestli jde o číslo sudé nebo liché, černé nebo červené,
nebo je to nula.

### Řešení

*Poznámka: použijeme speciální konstrukci `a = 1 if podminka else 2`.  
Například v tomto případě, pokud bude podmínka splněna, `a = 1`, v opačném případě `a = 2`.*

```python
cislo = int(input('Zadej čislo: '))

if cislo == 0:
  print('Číslo je 0.')
  exit()

je_sude = cislo % 2 == 0
sude_liche_text = 'sudé' if je_sude else 'liché'

if 1 <= cislo <= 10 or 19 <= cislo <= 28:
  barva = 'černé' if je_sude else 'červené'
else:
  barva = 'červené' if je_sude else 'černé'

print(f'Číslo je {sude_liche_text} a {barva}.')
```

## 5 - Soutěž ◆◆◆◆◆

Divadlo Pěst na oko pořádá soutěž o lístky na premiéru nového představení Zločin v podmínce. Pro účast v soutěži musí
zájemce splnit následující dvě podmínky:

Sdílel alespoň 5 příspěvků divadla na sociálních sítích.
Letos navštívil(a) alespoň 5 představení.
Současně platí, že soutěžit můžou všichni členové Klubu přátel Divadla Pěst na oko, i kdyby podmínky nesplnili.

Tvým úkolem je vytvořit program, který se uživatele zeptá na všechny potřebné informace (stačí odpověď ano/ne) a
vyhodnotí, zda se může zúčastnit soutěže.

### Řešení

```python
sdileni = input('Sdílel jsi alespoň 5 příspěvků na sociálních sítích? [a/n]: ')
pet_predstaveni = input('Navštívil jsi letos alespoň 5 představení? [a/n]: ')
clen_klubu = input('Jsi člen kubu? [a/n]: ')

if (sdileni == 'a' and pet_predstaveni == 'a') or clen_klubu == 'a':
  print('smíš soutěžit')
else:
  print('bohužel nesoutěžíš')
```
