## Jednoduchý výstup ◇◇◇◆◆

Náš vůbec první program nebude dělat nic víc, než vypisovat text na obrazovku.

- Založte si program `vstup_vystup.py`. V tomto programu pomocí funkce `print()` vypište na obrazovku `Divadlo Pěst na
  oko`. Program spusťte na konzoli a vyzkoušejte, že dělá co má.
- Upravte tento program tak, že do proměnné `nazev` uložíte název nějakého divadelního představení a do proměnné `cas`
  uložte čas konání tohoto představení. Nyní pomocí funkce `print()` nechte program vypsat na obrazovku na jeden řádek
  název představení a čas konání, např. `Zkrocení zlé ženy - 19:30`.
- Upravte dále program tak, že do proměnné `hodina` uložíte hodinu konání představení (jako celé číslo) a do proměnné
  `minuta` minutu konání, také jako celé číslo. Zařiďte, aby výstup programu vypadal takto: `Zkrocení zlé ženy - 19:30`.
  Pozor na to, že hodina a minuta je hodnota typu číslo, takže ji budete při výpisu muset převést na řetězec pomocí
  funkce `str()`[^1].

[^1]: V zadání na stránkách bylo opomenuto, že `minuta` může obsahovat i jednomístnou čísloci např.: 5. V řešení níže je
na to pamatováno pomocí [formátování](https://docs.python.org/3/library/string.html#format-specification-mini-language)
v `f`stringu.

### Řešení

```python
# vstup_vystup.py

print('Divadlo Pěst na oko')
nazev = 'Zkrocení zlé ženy'
cas = '19:30'
print(f'{nazev} - {cas}')

hodina = 19
minuta = 30
print(f'{nazev} - {hodina}:{minuta:02}')
```