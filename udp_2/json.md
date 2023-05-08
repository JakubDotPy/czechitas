# Cvičení: JSON

## 1 - Závod ◇◇◆◆◆

Pracuj dál se souborem `zavod.json` a zjisti čas závodníka, který získal stříbrnou medaili. Dále projdi data pomocí
cyklu a vytvoř seznam všech závodníků, kteří závod dokončili, tj. jejich oficiální čas není DNF.

Můžeš postupovat následujícím způsobem:

- Vytvoř si prázdný seznam `finishers`, kam budeš vkládat jména závodníků, kteří závod doběhli.
- Pomocí cyklu projdi seznam závodníků. Struktura vyjmuté položky bude obdobná jako struktura dat o vítězi závodu. Do
  cyklu vlož podmínku, která ověří, zda oficiální čas závodníka je odlišná od řetězce DNF.
- Dovnitř podmínky vlož kód, který vloží jméno závodníka do seznamu `finishers`.
- Na konec programu (mimo cyklus) vlož příkaz na vypsání obsahu seznamu `finishers`.

### Řešení

```python
import json

with open('zavod.json', encoding='utf-8') as file:
    runners = json.load(file)

finishers = []

for runner in runners:
    if runner['casy']['oficialni'] != 'DNF':
        finishers.append(runner['jmeno'])

print(finishers)
```

## 2 - Transformace dat ◇◆◆◆◆

Stáhněte si soubor `words.txt` a zpracujte z něj výstupní soubor ve formátu JSON obsahující slovník. Klíče budou písmena
a hodnoty seznamy slov, které začínají písmenem v klíči. Pokud na nějaké písmeno žádná slova nezačínají, tak ve výstupu
toto písmeno nebude. Seřaďte tyto seznamy podle abecedy. Zajistěte, aby i klíče ve výstupním JSON souboru byly seřazeny
a data byla odsazena čtyřmi mezerami pro lepší čitelnost člověkem.

Vzorový výstup: output.json.

### Řešení

```python
import json

words = {}

with open('words.txt', encoding='utf-8') as file:
    for word in file:
        first_letter = word[0]
        if first_letter not in words:
            words[first_letter] = [word]
        words[first_letter].append(word)

for value in words.values():
    value.sort()

with open('output.json', 'w', encoding='utf-8') as out:
    json.dump(words, out, sort_keys=True, indent=4, ensure_ascii=False)
```

# Cvičení: JSON

## 1 - Kurz ◇◇◆◆◆

Stáhněte si soubor `kurz.json` s výše uvedeným obsahem a načtěte jej v Pythonu do proměnné `kurz`. Odpovězte na následující
otázky:

- Vypište na výstup počet účastnic na posledním konání kurzu.
- Vypište na výstup jméno posledního kouče na prvním konání kurzu.
- Vypište na výstup celkový počet konání kurzu.
- Vypište na výstup všechna místa, na kterých se kurz konal.
- Vypište na výstup součet všech účastnic.
- Vypište na výstup množinu všech koučů, kteří se kdy kurzu účastnili.

### Řešení

```python
import json

with open('in.txt', encoding='utf-8') as f:
    data = json.load(f)

print(data['konani'][-1]['ucastnic'])

print(data['konani'][0]['koucove'][-1])

print(len(data['konani']))

mista = []
for konani in data['konani']:
    mista.append(konani['misto'])
print(mista)

ucastnice = 0
for konani in data['konani']:
    ucastnice += konani['ucastnic']
print(ucastnice)

koucove = set()
for konani in data['konani']:
    koucove.update(set(konani['koucove']))
print(koucove)
```

---

# Cvičení: API a JSON

## 1 - Seznam lidí ◇◇◇◆◆

Jak už jsme si ověřili v lekci, datové API na adrese https://api.kodim.cz/python-data/people obsahuje seznam lidí.
Napište program, který tento seznam z API stáhne a převede z formátu JSON na Python slovníky. Proveďte následující
úkoly.

- Zjistěte kolik lidí celkem seznam obsahuje.
- Zjistěte jaké všechny informace máme o jednotlivých osobách.
- Zjistěte, kolik je v souboru mužů a žen.

### Řešení

```python
import requests

resp = requests.get('https://api.kodim.cz/python-data/people')
data = resp.json()

print(f'pocet lidi {len(data)}')

print(f'o osobach vime {list(data[0].keys())}')

pocet_muzu = 0
for clovek in data:
    if clovek['gender'] == 'Male':
        pocet_muzu += 1
print(f'soubor obsahuje {pocet_muzu} a {len(data) - pocet_muzu} zen')
```

## 2 - Svátky ◇◇◆◆◆

Na adrese https://svatky.adresa.info/json najdete API, které vám odpoví, kdo má dneska svátek.

- Využijte toto API k tomu, abyste napsali program, který po spuštění vypíše na obrazovku kdo má dneska svátek.
- Pokud použijete adresu https://svatky.adresa.info/json?date=DDMM, kde místo DDMM doplníte datum, dostanete jméno,
  které má svátek v zadaný den. Formát DDMM znamená že 6. ledna bude zapsáno jako 0601, 12. září jako 1209 apod. Napište
  program, který dostane na příkazové řádce číslo dne a číslo měsíce a vypíše na výstup kdo má v daný den svátek.
  Použijte váš program abyste zjistili, kdo má svátek 29. února.
- Bonus: předchozí bod uprav tak, že nebudeš dávat funkci `requests.get()` adresu včetně parametru `date=1209`, ale pouze
  základní "endpoint" https://svatky.adresa.info/json a parametry (vše za `?`) dodáš volitelným parametrem. Budeš
  potřebovat pracovat s dokumentací k requests.

### Řešení

V případně nedostupnosti API kod skončí chybou "TimeoutError".

```python
import requests

resp = requests.get('https://svatky.adresa.info/json', timeout=3)
data = resp.json()
print(f'dnes ma svatek {data[0]["name"]}')

datum = input('Zadej datum [DDMM]: ')
#
resp = requests.get(f'https://svatky.adresa.info/json?date={datum}', timeout=3)
data = resp.json()
print(f'dnes ma svatek {data[0]["name"]}')

# pomoci params
resp = requests.get(f'https://svatky.adresa.info/json', params={'date': datum}, timeout=3)
data = resp.json()
print(f'dnes ma svatek {data[0]["name"]}')
```