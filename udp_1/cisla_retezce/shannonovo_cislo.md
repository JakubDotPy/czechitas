## Shannonovo číslo

- Takzvané Shannonovo číslo má hodnotu 10^120 a udává kolik nejméně lze odehrát různých šachových partií. Vytvořte
  řetězec, který obsahuje toto číslo zapsané běžným způsobem pomocí cifer. Například 10^3 je 1000, 10^6 je 1000000
  atd.
- Čísla s mnoha nulami je v Česku zvykem zapisovat tak, že každé tři nuly následuje mezera. Jeden milión se tedy zapíše
  jako 1 000 000. Vytvořte řetězec, který obsahuje Shannonovo číslo z předchozího cvičení zapsané v tomto formátu.

<details>
<summary><b>Řešení</b></summary>

```python
print('1' + '0' * 120)
```

```python
print('1' + ' 000' * (120 // 3))
```

</details>
