## Ruleta

Na obrázku vidíte rozložení čísel na klasické Francouzské ruletě. Ruleta obsahuje čísla `0 - 36`. Každé číslo s výjimkou
nuly je buď sudé nebo liché a zároveň červené nebo černé. Pro čísla 1 až 10 a 19 až 28 platí, že lichá čísla jsou
červená a sudá jsou černá. Pro zbytek platí obrácené pravidlo, tedy lichá jsou černá a sudá červená. Nula není ani lichá
ani sudá, ani černá ani červená.

![Ruleta](https://kodim.cz/cms/assets/kurzy/uvod-do-progr-1/prvni-krucky/podminky/cteni-na-doma/excs%3Eruleta/roulette.png)

Napište program, kterému uživatel zadá číslo a program odpoví jestli jde o číslo sudé nebo liché, černé nebo červené,
nebo je to nula.

<details>
<summary><b>Řešení</b></summary>


*Poznámka: použijeme speciální konstrukci `a = 1 if podminka else 2`.  
Například v tomto případě, pokud bude podmínka splněna, `a = 1`, v opačném případě `a = 2`.*

```python
cislo = int(input('Zadej čislo: '))

if cislo == 0:
  print('Číslo je 0.')
  exit()

je_sude = cislo % 2 == 0
sude_liche_text = 'sudé' if je_sude else 'liché'

if 1 <= cislo <= 10 or 19 <= cislo <= 28:
  barva = 'černé' if je_sude else 'červené'
else:
  barva = 'červené' if je_sude else 'černé'

print(f'Číslo je {sude_liche_text} a {barva}.')
```

</details>
