## Elegantní volby ◇◆◆◆◆

Pokud vás trápí, že řešení varianty e) v úloze o volbách není příliš elegantní, zkuste sestavit Python výraz na jeden řádek, 
který celý bod e) vyřeší najednou. Bude potřeba do sebe zanořit dvě chroustání seznamů, jedno přes hodnoty v řádcích a druhé přes jednotlivé kraje.

<details>
<summary><b>Řešení</b></summary>


```python
# procenta celkoveho poctu
procenta = [
    [round((kandidat / sum(kraj)) * 100, 2) for kandidat in kraj]
    for kraj in hlasy
]
print(procenta)
```

</details>
