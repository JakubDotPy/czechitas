## Seznam balíků podruhé ◇◇◆◆◆

Vedení společnosti si uvědomilo, že do hodnoty balíků v autě by se neměly započítávat balíky, které už byly doručeny,
protože již byly předány příjemci a nebudou tedy ukradeny nebo zničeny.

- Uprav kód, který vytváří balíky, aby byl jeden balík vytvořený ve stavu `doručen`.
- Uprav cyklus, aby započítal hodnotu pouze těch balíků, které jsou ve stavu `nedoručen`. Je třeba k této kontrole
  využít funkci `hasattr()`?

### Řešení

```python
for package in package_list:
    if hasattr(package, 'value') and package.state == "nedoručen":
        total_value += package.value
```