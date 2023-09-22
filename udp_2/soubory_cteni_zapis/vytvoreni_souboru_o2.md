## Vytvoření souboru ◇◇◇◆◆

Napište program, který se po spuštění zeptá na název souboru, který má vytvořit (nebo přepsat, pokud už ten soubor existuje), a pak se zeptá na řádek textu, který má do souboru zapsat.

<details>
<summary><b>Řešení</b></summary>


```python
jmeno_souboru = input('Zadej nazev souboru: ')
radek = input('co chceš zapsat?: ')

with open(jmeno_souboru, 'w', encoding='utf-8') as f:
    f.write(radek)
```


</details>
