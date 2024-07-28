## Ověřování věku

Následující seznam obsahuje věky uživatelů naší malé sociální sítě.

```python
veky = [35, 12, 44, 11, 18, 21, 28, 18]
```

- Vytvořte pomocí chroustání seznamů seznam celých čísel, které udávají, kolik jednotlivým uživatelům zbývá do 18ti let.
  Záporná čísla budou znamenat, že uživatel už věk překročil.
- Vytvořte pomocí chroustání seznamů seznam pravdivostních hodnot, které udávají, který uživatel je starší 18ti let.
- Vytvořte pomocí chroustání seznamů seznam pravdivostních hodnot, které udávají, který uživatel má přesně 18 let.

<details>
<summary><b>Řešení</b></summary>

```python
zbyva_do_18 = [18 - vek for vek in veky]
starsi_18 = [vek > 18 for vek in veky]
stary_presne_18 = [vek == 18 for vek in veky]
```

</details>
