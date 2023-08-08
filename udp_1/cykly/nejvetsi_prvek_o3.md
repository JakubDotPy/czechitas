## Největší prvek ◇◇◆◆◆

Napište cyklus, který projde zadaný seznam celých čísel a najde v něm největší hodnotu.

### Řešení

```python
cisla = [11, 23, 45, 1, 9, 65, 34]
nejvetsi = cisla[0]
for cislo in cisla:
    if cislo > nejvetsi:
        nejvetsi = cislo
print(nejvetsi)
```