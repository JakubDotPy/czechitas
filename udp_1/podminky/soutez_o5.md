## Soutěž ◆◆◆◆◆

Divadlo Pěst na oko pořádá soutěž o lístky na premiéru nového představení Zločin v podmínce. Pro účast v soutěži musí
zájemce splnit následující dvě podmínky:

Sdílel alespoň 5 příspěvků divadla na sociálních sítích.
Letos navštívil(a) alespoň 5 představení.
Současně platí, že soutěžit můžou všichni členové Klubu přátel Divadla Pěst na oko, i kdyby podmínky nesplnili.

Tvým úkolem je vytvořit program, který se uživatele zeptá na všechny potřebné informace (stačí odpověď ano/ne) a
vyhodnotí, zda se může zúčastnit soutěže.

<details>
<summary><b>Řešení</b></summary>


```python
sdileni = input('Sdílel jsi alespoň 5 příspěvků na sociálních sítích? [a/n]: ')
pet_predstaveni = input('Navštívil jsi letos alespoň 5 představení? [a/n]: ')
clen_klubu = input('Jsi člen kubu? [a/n]: ')

if (sdileni == 'a' and pet_predstaveni == 'a') or clen_klubu == 'a':
  print('smíš soutěžit')
else:
  print('bohužel nesoutěžíš')
```


</details>
