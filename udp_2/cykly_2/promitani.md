## Promítání

V letním kině Šmajchl mají program na každý den uložený jako dva seznamy. První seznam obsahuje názvy filmů a druhý
jejich délky v minutách, např. takto:

```python
nazvy = [
    'Někdo to rád horké, extended edition',
    'Adéla ještě nevečeřela',
    'Kulový blesk'
]
delky = [136, 105, 82]
```

Použijte chroustání seznamů a vyrobte seznam trvání, který bude obsahovat délky filmů nikoliv jako čísla v minutách, ale
jako řetězce v hodinách a v minutách. Výsledek tedy bude vypadat takto

```python
trvani = ['2:16', '1:45', '1:22']
```

<details>
<summary><b>Řešení</b></summary>

```python
trvani = [f'{d // 60}:{d % 60}' for d in delky]
```

</details>
