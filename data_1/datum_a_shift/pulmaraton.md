## Půlmaraton

Uvažuj časy závodníků za ročníky půlmaratonu 2019 a 2020, které jsou uloženy v
souboru [half_marathon.csv](https://kodim.cz/cms/assets/czechitas/python-data-1/python-pro-data-1/datum-cas-shift/excs/pulmaraton/half_marathon.csv).
V souboru je uloženo jméno závodníka (závodnice), rok narození, jeho/její čas a rok závodu, ke kterému se čas vztahuje.
Tvým úkolem je spočítat, o kolik se změnil průměrný čas každého ze závodníků a závodnic a zda se v průměru zlepšili či
zhoršili (například protože kvůli lockdownům méně trénovali).

Můžeš využít následující postup:

- Převeď sloupec s časem závodníka na typ datetime. Použij stejný postup, jaký jsme si ukázali v minulé v lekci. Protože
  jde pouze o časový údaj, pandas k němu připojí dnešní datum, aby byly ve sloupci datum i čas. Toho si ale nevšímej, u
  obou sloupců je datum stejný, takže na porovnání údajů to nebude mít vliv.
- Pomocí metody `shift()` si dej na jeden řádek výsledky obou závodů. Metodu `shift()` použij tak, aby nový sloupec
  obsahoval hodnoty posunuté o jeden řádek dolů. Je třeba nahradit X vhodně zvoleným číslem. Poté si nech v datech pouze
  data, která mají ve sloupci `Rok zavodu` hodnotu 2020. Řádky, které mají ve sloupci `Rok zavodu` hodnotu 2019, totiž
  obsahují "pomíchané" hodnoty dvou různých závodníků.
- Vypočítej rozdíl mezi časy závodníka a převeď ho na sekundy (postup jsme si ukazovali v lekci). Dále spočítej
  průměrnou změnu. Vyšlo i kladné nebo záporné číslo? A co to znamená?

<details>
<summary><b>Řešení</b></summary>

```python
# TODO: add solution
```

</details>
