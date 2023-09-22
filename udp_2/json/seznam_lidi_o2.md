## Seznam lidí ◇◇◇◆◆

Jak už jsme si ověřili v lekci, datové API na adrese https://api.kodim.cz/python-data/people obsahuje seznam lidí.
Napište program, který tento seznam z API stáhne a převede z formátu JSON na Python slovníky. Proveďte následující
úkoly.

- Zjistěte kolik lidí celkem seznam obsahuje.
- Zjistěte jaké všechny informace máme o jednotlivých osobách.
- Zjistěte, kolik je v souboru mužů a žen.

<details>
<summary><b>Řešení</b></summary>


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

</details>
