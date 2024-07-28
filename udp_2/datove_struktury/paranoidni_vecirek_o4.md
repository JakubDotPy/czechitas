## Paranoidní večírek

Pořadatel našeho večírku se stává stále více paranoidním a nyní rozhodl, že každý z hostů bude mít speciální heslo,
které je platné jen pro něj. Seznam hostů a jejich hesel je níže.  
Napiš program, který nejprve zkontroluje, zda je host na seznamu, a pokud tam je,zeptá se ho na heslo a zkontroluje jeho
správnost.  
Hostu na seznamu, který zadá správné heslo, vypíše program text: `"Smíš vstoupit."`

<details>
<summary><b>Řešení</b></summary>


```python
hesla = {
    'Jiří'   : 'tajne-heslo',
    'Natálie': 'jeste-tajnejsi-heslo',
    'Klára'  : 'nejtajnejsi-heslo',
}

jmeno_hosta = input('Zadej jmeno: ')
vstup = 'Nesmíš projít.'

if jmeno_hosta in hesla:
    heslo = input('Zadej heslo: ')
    if heslo == hesla[jmeno_hosta]:
        vstup = 'Smíš vstoupit.'

print(vstup)
```

</details>
