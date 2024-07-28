## Gymnázium

Modifikujme si předchozí příklad. Horší známku z matematiky může student kompenzovat tím, že uspěje v matematické
olympiádě.  
Přidejte tedy dotaz, zda se uchazeč zúčastnil okresního kola matematické olympiády. Pokud ano, bude mu zkouška
odpuštěna, i kdyby jeho známka z matematiky byla horší. Požadavek na celkový průměr známek je však třeba stále dodržet.

Otázka může vypadat například takto:  
`input("Zúčastnil ses okresního kola krajské olympiády? [a/n] ")`

Pokud se student olympiády zúčastnil, odpoví `a`.

<details>
<summary><b>Řešení</b></summary>

```python
matematika_znamka = int(input('Zadej známku z matematiky: '))
prumer_vysvedceni = float(input('Zadej průměr z vysvědčení: '))
olympiada = input("Zúčastnil ses okresního kola krajské olympiády? [a/n] ")

if prumer_vysvedceni < 1.8 and (matematika_znamka <= 2 or olympiada == 'a'):
  print('Přijmeme vás bez přijímací zkoušky.')
else:
  print('Musíte splnit přijímací zkoušku.')
```

</details>
