## Zasedačka

Níže máš seznam akcí, které se konaly v zasedačce jedné firmy.

```python
akce = [
    "školení - řízení firemních vozidel",
    "jazykový kurz - angličtina",
    "pohovor - Jan Dvořák",
    "pohovor - Antonín Sova",
    "jazykový kurz - němčina",
    "pohovor - Iveta Hájková",
    "pohovor - Ivan Brož",
    "pohovor - Katarína Martináková",
    "setkání se zákazníkem - Metrostav",
    "jazykový kurz - angličtina",
    "školení - vykazování práce",
    "pohovor - Klaudie Moudrusová",
]
```

Napiš program, který zjistí následující:

- Kolik se uskutečnilo pohovorů?
- V jakých jazycích se mohou zaměstnanci firmy vzdělávat?

Při řešení můžeš využít operátor `in` a slicing, případně metodu `split()`

<details>
<summary><b>Řešení</b></summary>

```python
dostupne_jazyky = []
pocet_pohovoru = 0

for radek_text in akce:

    # rozdelim a ulozim do dvou promennych
    radek = radek_text.split(' - ')
    typ = radek[0]
    data = radek[1]

    if typ == 'jazykový kurz':
        # musime zkontrolovat, jestli uz v seznamu nemame
        if data not in dostupne_jazyky:
            dostupne_jazyky.append(data)

    if typ == 'pohovor':
        pocet_pohovoru += 1

print(f'dostupne jazyky jsou {dostupne_jazyky}')
print(f'bylo {pocet_pohovoru} pohovoru')
```

</details>
