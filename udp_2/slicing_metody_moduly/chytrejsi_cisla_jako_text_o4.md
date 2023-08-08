## Chytřejší čísla jako text ◇◆◆◆◆

Zkuste vymyslet, jak udělat zápis příkazů ze cvičení `Čísla jako text` co nejúspornější.  
Dá se dojít až k tomu, že celé řešení bude na jeden řádek.

### Řešení

```python
hodnoty = ['12', '1', '7', '-11']
hodnoty[2] = str(int(hodnoty[2]) + 4)
print(hodnoty)
```
