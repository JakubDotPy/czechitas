## Přijímačky a moduly ◇◇◇◆◆

Uvažujme vysvědčení studenta, které máme uložené jako seznam.

```python
school_report = [
    ["Český jazyk", 1],
    ["Anglický jazyk", 1],
    ["Matematika", 1],
    ["Přírodopis", 2],
    ["Dějepis", 1],
    ["Fyzika", 2],
    ["Hudební výchova", 4],
    ["Výtvarná výchova", 2],
    ["Tělesná výchova", 3],
    ["Chemie", 4],
]
```

Uvažuj, že student se hlásí na školu, která vybírá studenty podle průměru.  
Pro školu jsou ale důležité pouze předměty český jazyk, anglický jazyk, matematika a fyzika. Vypočítej průměr studenta z
daných předmětů s využitím modulu `statstics`.  
Na začátku vytvoř prázdný seznam a následně pomocí cyklu vlož do nového seznamu známky ze čtyř vyjmenovaných předmětů.
Nakonec použij metodu `statistics.mean()` k výpočtu průměru.
Dále zkus využít funkce, které jsou zmíněné v textu, k výpočtu nejlepší a nejhorší známky z daných předmětů.

<details>
<summary><b>Řešení</b></summary>


```python
import statistics

sledovane_predmety = [
    'Český jazyk',
    'Anglický jazyk',
    'Matematika',
    'Fyzika',
]

sledovane_znamky = []

for predmet_znamka in school_report:
    # rozdelime si dvojici na dve samostatne promenne pro lepsi praci
    predmet = predmet_znamka[0]
    znamka = predmet_znamka[1]
    if predmet in sledovane_predmety:
        sledovane_znamky.append(znamka)

print(f'průměr sledovaných předmětů je {statistics.mean(sledovane_znamky)}')
print(f'nejlepší je {min(sledovane_znamky)}')
print(f'nejhorší je {max(sledovane_znamky)}')
```


</details>
