## Přeznámkování ◇◇◇◆◆

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