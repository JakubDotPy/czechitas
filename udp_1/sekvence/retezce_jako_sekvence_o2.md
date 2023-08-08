## Řetězce jako sekvence ◇◇◇◆◆

- Uložte do proměnné `jmeno` svoje celé jméno a nechte vypsat jeho třetí, pátý a sedmý znak.  
  Vyzkoušejte, co se stane, když budete chtít znak na pozici, která překračuje délku řetězce.

### Řešení

```python
uzivatel = input('Zadej uživatelské jméno: ')
print(uzivatel[2])
print(uzivatel[4])
print(uzivatel[6])
print(uzivatel[60])
```