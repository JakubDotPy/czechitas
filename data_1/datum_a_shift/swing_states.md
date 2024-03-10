## Swing states

V případě amerických prezidentských voleb obecně platí, že ve většině států dlouhodobě vyhrávají kandidáti jedné strany.
Například v Kalifornii vyhrávají poměrně dlouho kandidáti Demokratické strany, v Texasu zase kandidáti Republikánské
strany. Státy, kde se vítězné strany střídají, jsou označovány jako _swing states_ ("kolísavé státy"). Tvým úkolem je
pro jeden konkrétní stát spočítat, kolikrát v něm došlo ke změně vítězné strany, přičemž data jsou uložena v
souboru [election-data.csv](https://kodim.cz/cms/assets/czechitas/python-data-1/python-pro-data-1/datum-cas-shift/excs/swing-states/election-data.csv).

V souboru jsou důležité následující sloupce:

`year` - rok voleb,
`state` - stát,
`party_simplified` - zjednodušené označení politické strany,
`rank` - pořadí kandidáta v rámci státu a roku.

Vyber si jeden stát, např. stát PENNSYLVANIA. Vytvoř si tabulku, kde budou data pouze za tento stát. Současně si vyber
pouze data o vítězích, tj. řádky, které mají ve sloupci `rank` hodnotu `1`. Vytvoř sloupec, který bude obsahovat
politickou strunu vítěze voleb z přechozího volebního období. Pokud spočítáš řádky, kde se politická strana současného
vítěze liší od strany minulého, zjistíš, kolikrát voliči v daném státě přešli od jedné strany ke druhé. Pozor na to, že
pro rok 1976 neznáme předchozího vítěze, v nově přidaném sloupci tedy bude prázdná hodnota. Té se můžeš zbavit například
pomocí metody `dropna()`.

Např. pro stát PENNSYLVANIA by ti mělo vyjít, že ke změně došlo celkem čtyřikrát, a to v letech 1980, 1992, 2016 a 2020.
Ve státě SOUTH CAROLINA došlo ke změně pouze jednou, a to v roce 1980, kdy vyhrál Ronald Reagan. Od té doby zde
vyhrávají pouze kandidáti Republikánské strany.


<details>
<summary><b>Řešení</b></summary>

```python
# TODO: add solution
```

</details>