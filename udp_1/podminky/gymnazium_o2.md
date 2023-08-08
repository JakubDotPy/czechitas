## Gymnázium ◇◇◇◆◆

Matematické gymnázium nabízí aplikaci, která sděluje informaci o povinnosti vykonání přijímací zkoušky.  
Požádejte uživatele o zadání známky z matematiky a průměru všech známek na posledním vysvědčení.  
Pokud má zájemce průměr známek nižší než 1.8 a z matematiky nejhůře dvojku, vypište
text: `"Přijmeme vás bez přijímací zkoušky."`.
V opačném případě vypište `"Musíte splnit přijímací zkoušku."`.

### Řešení

```python
matematika_znamka = int(input('Zadej známku z matematiky: '))
prumer_vysvedceni = float(input('Zadej průměr z vysvědčení: '))

if prumer_vysvedceni < 1.8 and matematika_znamka <= 2:
  print('Přijmeme vás bez přijímací zkoušky.')
else:
  print('Musíte splnit přijímací zkoušku.')
```