## Seznam hostů na párty

Vraťte se k příkladu se zadáváním seznamu hostu na párty a zkopírujte si kód k sobě do editoru.  
Upravte program tak, že pokud uživatel v průběhu zadávání jmen napíše "konec", cyklus na zadávání jmen se ukončí.

<details>
<summary><b>Řešení</b></summary>


```python
number_of_guests = int(input("Zadej počet hostů: "))
guest_list = []
for i in range(number_of_guests):
    new_guest = input("Zadej jméno hosta: ")
    if new_guest == 'konec':
        break
    guest_list.append(new_guest)
print(guest_list)
```

</details>
