## Závod ◇◇◆◆◆

Pracuj dál se souborem `zavod.json` a zjisti čas závodníka, který získal stříbrnou medaili. Dále projdi data pomocí
cyklu a vytvoř seznam všech závodníků, kteří závod dokončili, tj. jejich oficiální čas není DNF.

Můžeš postupovat následujícím způsobem:

- Vytvoř si prázdný seznam `finishers`, kam budeš vkládat jména závodníků, kteří závod doběhli.
- Pomocí cyklu projdi seznam závodníků. Struktura vyjmuté položky bude obdobná jako struktura dat o vítězi závodu. Do
  cyklu vlož podmínku, která ověří, zda oficiální čas závodníka je odlišná od řetězce DNF.
- Dovnitř podmínky vlož kód, který vloží jméno závodníka do seznamu `finishers`.
- Na konec programu (mimo cyklus) vlož příkaz na vypsání obsahu seznamu `finishers`.

<details>
<summary><b>Řešení</b></summary>


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

</details>
