## Kurz ◇◇◆◆◆

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