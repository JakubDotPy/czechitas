## Spolubydlící

Zkus dotáhnout náš program na finanční vypořádání spolubydlících. Z lekce si můžeš zkopírovat kódy, které vytvoří slovník s útratami jednotlivých spolubydlících a výpočet průměrné útraty na osobu.  
Dopiš cyklus, který projde slovník `sum_per_person` a pro každého ze spolubydlících vypíše, kolik by měl doplatit (pokud utratil(a) méně než průměr), případně kolik by měl obdržet (pokud utratil(a) více než průměr).

<details>
<summary><b>Řešení</b></summary>


```python
import statistics

purchase_list = [
    {"Jméno": "Petr", "Položka": "Prací prášek", "Částka": 399},
    {"Jméno": "Ondra", "Položka": "Savo", "Částka": 80},
    {"Jméno": "Petr", "Položka": "Toaletní papír", "Částka": 65},
    {"Jméno": "Libor", "Položka": "Pivo", "Částka": 124},
    {"Jméno": "Petr", "Položka": "Pytel na odpadky", "Částka": 75},
    {"Jméno": "Míša", "Položka": "Utěrky na nádobí", "Částka": 130},
    {"Jméno": "Ondra", "Položka": "Toaletní papír", "Částka": 120},
    {"Jméno": "Míša", "Položka": "Pečící papír", "Částka": 30},
    {"Jméno": "Zuzka", "Položka": "Savo", "Částka": 80},
    {"Jméno": "Pavla", "Položka": "Máslo", "Částka": 50},
    {"Jméno": "Ondra", "Položka": "Káva", "Částka": 300}
]

# vytvoříme slovník
sum_per_person  = {}

for polozka in purchase_list:
    person = polozka['Jméno']
    value = polozka['Částka']

    # get nám dá hodnotu, pokud je ve slovníku, nebo zadanou hodnotu (zde 0)
    sum_per_person[person] = sum_per_person.get(person, 0) + value

average_value = statistics.mean(sum_per_person.values())

for person, value in sum_per_person.items():

    diff = round(value - average_value)

    if diff > 0:
        print(f'{person} dostane {diff}')
    elif diff < 0:
        print(f'{person} zaplati {abs(diff)}')
    else:
        print(f'{person} je na nule')
```

</details>
