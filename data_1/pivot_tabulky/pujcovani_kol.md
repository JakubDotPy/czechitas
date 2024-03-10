## Půjčování kol

V
souboru [london_merged.csv](https://kodim.cz/cms/assets/czechitas/python-data-1/python-pro-data-1/pivot-tabulky/dalsi-funkce/kola/london_merged.csv)
najdeš informace o počtu vypůjčení jízdních kol v Londýně. Vytvoř kontingenční tabulku, zobrazí průměrný počet reze (
sloupec `weather_code` se sloupcem udávající měsíc). Počet vypůjčených kol je ve sloupci `cnt`. V datech je dále
sloupec `Hour`, který označuje hodinu, pro který počet máme. Použij kód z předchozí části a rozděl data do kategorií
podle denní doby. Vytvoř pivot tabulku, která zobrazí průměrné počty vypůjčených kol v závislosti na typu počasí (
sloupec `weather_code`) a denní době.

Definice jednotlivých kódů ze sloupce `weather_code` jsou:

- 1 = Jasno; includes minor atmospheric conditions like haze, fog, patches of fog, or fog in the vicinity.
- 2 = Částečně oblačno; indicating a sky that is partly cloudy with scattered or few clouds.
- 3 = Převážně oblačno; mostly covered with clouds, but not entirely overcast.
- 4 = Zataženo; indicating a fully overcast or cloudy sky.
- 7 = Déšť / Lehký déšť; covering light rain conditions, including light rain showers.
- 10 = Déšť s bouřkou; rain accompanied by a thunderstorm.
- 26 = Sněžení; general condition of snow falling.
- 94 = Mrznoucí mlha; indicating fog conditions where the water droplets in the fog freeze upon contact with surfaces.

Pokud ti zobrazení pomocí číselných kódů přijde nepřehledné, můžeš kódy nahradit popisy. K tomu lze využít metodu `map`.
Pro metodu `map` je nutné mít tzv. slovník, tj. strukturu, která obsahuje data ve dvojicích. Hodnoty ve dvojici jsou
odděleny dvojtečkou a celá dvojice je oddělená čárkou. V našem případě máme slovník `weather_code_to_czech`, kde máme
číselný kód a popisek hodnoty pro každé počasí. Výsledek poté uložíme do sloupce `weather_description`. Vyzkoušej kód
níže a podívej se, zda skutečně v tabulce přibyl sloupec `weather_description` a zda hodnoty odpovídají číselným kódům.

```py
weather_code_to_czech = {
    1 : "Jasno",
    2 : "Částečně oblačno",
    3 : "Převážně oblačno",
    4 : "Zataženo",
    7 : "Déšť / Lehký déšť",
    10: "Déšť s bouřkou",
    26: "Sněžení",
    94: "Mrznoucí mlha"
}
data['weather_description'] = data['weather_code'].map(weather_code_to_czech)
```

<details>
<summary><b>Řešení</b></summary>

```python
# TODO: add solution
```

</details>