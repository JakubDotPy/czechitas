# Cvičení

## 1 - Řetězce jako sekvence ○○○♦♦

- Uložte si v Python konzoli do proměnné jmeno svoje celé jméno a nechte vypsat jeho třetí, pátý a sedmý znak.
  Vyzkoušejte, co se stane, když budete chtít znak na pozici, která překračuje délku řetězce.
- Upravte program `registrace.py` tak, že bude kromě uživatelského jména chtít také e-mailovou adresu. Ověřte, že adresa
  je v platném formátu, tedy že obsahuje zavináč, tečku a má alespoň pět znaků.

### Řešení

```python
uzivatel = input("Zadej uživatelské jméno: ")
uzivatel[2]
uzivatel[4]
uzivatel[6]
```

```python
# resgistrace.py

uzivatel = input('Zadej uživatelské jméno: ')

email = input("Zadej emailovou adresu: ")
if '@' not in email or '.' not in email or len(email) < 5:
    print('Emailova adresa není v platném formátu. Musí obsahovat zavináč, tečku a mít alespoň 5 znaků.')
    exit()

heslo = input('Zadej heslo: ')
if len(heslo) <= 8:
    print('Heslo je příliš krátké')
    exit()

heslo_2 = input('Zadej heslo znovu: ')
if heslo != heslo_2:
    print('Hesla se neshodují.')
```

## 2 - Seznamy ○♦♦♦♦

Celé toto cvičení dělejte v příkazové řádce Pythonu.

- Vytvořte nějaký seznam celých čísel, například počty diváků na několika po sobě jdoucích představeních. Použije metodu
  `append` a přidejte do seznamu počet diváků na jednom dalším představení.
- Vytvořte nějaký seznam desetinných čísel, například zaplněnost divadla v několika po sobě jdoucích představeních.
- Vytvořte nějaký seznam řetězců, například seznam názvů několika divadelních představení, která divadlo hraje. Uložte
  tento seznam do proměnné hry. Uložte do nějaké proměnné druhou položku tohoto seznamu.
- Do proměnné `hodnoceni` uložte seznam hodnocení, které obdržela divadelní hra
  *Plyšáci na útěku* v různých recenzních časopisech. Hodnocení je vždy dvouprvkový seznam obsahující název recenzního
  časopisu jako řetězec a samotné hodnocení jako číslo mezi 1 až 10. Přidejte na konec tohoto seznamu nové hodnocení z
  časopisu *Divadelní oběžník*.

### Řešení

```python
pocty_divaku = [120, 100, 95, 78, 100]
pocty_divaku.append(113)
zaplnenost = [0.9, 0.8, 0.7, 0.65, 0.8, 0.85]
hry = ['Hra A', 'Hra B', 'Hra C', 'Hra D', 'Hra E', 'Hra F']
druha_hra = hry[1]
hodnoceni = [['Casopis A', 5], ['Casopis B', 8], ['Casopis C', 7]]
hodnoceni.append(['Divadelni obeznik', 7])
```

# Bonusy

## 3 - Ověřování hesla ○○♦♦♦

Ověřování hesla se někdy dělá tak, že se vás systém ptá pouze na některé jeho znaky. Napište program, který má uloženo
heslo, které musí uživatel zadat. Pak se jej postupně zeptejte například na druhý, pátý a sedmý znak hesla. Propusťte
uživatele pouze tehdy, zadá-li všechny tyto znaky správně.

### Řešení

```python
heslo = 'tajneHeslo345@'

znak = input('Zadej 2. znak hesla: ')
if znak != heslo[1]:
    print('Chyba ověření.')
    exit()
znak = input('Zadej 5. znak hesla: ')
if znak != heslo[4]:
    print('Chyba ověření.')
    exit()
znak = input('Zadej 7. znak hesla: ')
if znak != heslo[6]:
    print('Chyba ověření.')
    exit()
print('Ověření bylo úspěšné!')
```