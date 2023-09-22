## Seznamy řetězců ◇◇◇◆◆

Mějme zadaný následující seznam

```python
jmena = ['Roman', 'Jan', 'Miroslav', 'Petr', 'Gabriel']
```

Vytvořte seznam, který obsahuje

- počty písmen ve všech jménech,
- všechna jména napsaná velkými písmeny,
- všechna jména plus písmeno 'a' na konci (stanou se z nich tedy ženská jména),
- všechna jména převedená na malá písmena s koncovkou '@email.cz'.

<details>
<summary><b>Řešení</b></summary>


```python
pocty = [len(jmeno) for jmeno in jmena]
velkymi = [jmeno.upper() for jmeno in jmena]
s_ackem = [jmeno + 'a' for jmeno in jmena]
emaily = [f'{jmeno.lower()}@email.cz' for jmeno in jmena]
```

</details>
