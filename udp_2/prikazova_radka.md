# Cvičení: Parametry příkazové řádky

## 1 - Čas v minutách ◇◇◇◆◆

Napište program `minuty.py`, která dělá obrácenou věc než program `cas.py` z textu výše. Když mu na příkazové řádce
předáme dva parametry ‒ počet hodin a počet minut ‒ například takto

```text
python minuty.py 2 54
```

program nám vrátí délku tohoto času minutách. V tomto případě tedy číslo 174.

- Nejprve program napište tak, že si hodnoty 2 a 54 uložíte přímo natvrdo v programu do nějakých proměnných a z nich
  spočítáte a vytisknete výsledek.
- Až když váš program bude fungovat, zkuste tyto proměnné načíst z parametrů příkazové řádky. Nezapomeňte, že parametry
  jsou vždy řetězce a že první parametr je vždy název vašeho programu.

### Řešení

ukážeme si rovnou druhou variantu

```python
import sys

hodiny = int(sys.argv[1])
minuty = int(sys.argv[2])

print(hodiny * 60 + minuty)
```

## 2 - Úprava řetězce ◇◇◇◆◆

Napište program, který dostane jako jeden parametr řetězec s mezerami (aby to fungovalo, musí být ten řetězec obalen v
uvozovkách). Vypište tento řetězec tak, že mezery nahradíte za podtržítka.

```text
python uprava_retezce.py "retezec s mezerami"
retezec_s_mezerami
```

### Řešení

```python
import sys

retezec = sys.argv[1]
print(retezec.replace(' ', '_'))
```

## 3 - Jak proměnit hada na velblouda ◇◇◆◆◆

Napište program, který dostane na příkazovém řádku název proměnné v hadí notaci a vrátí tentýž název zapsaný ve velbloudí notaci.

Příklad:

```text
python had-velbloud.py had_honi_velblouda
hadHoniVelblouda
```

### Řešení

```python
import sys

retezec = sys.argv[1]

title_s_mezerami = retezec.replace('_', ' ').title()
prvni_male = title_s_mezerami[0].lower() + title_s_mezerami[1:]
vysledek = ''.join(prvni_male.split())

print(vysledek)
```

## 4 - Házení kostkou ◇◆◆◆◆

- Napište program, který při každém spuštění hodí šestistěnnou kostkou ‒ tedy vypíše náhodné číslo mezi 1 až 6.
- Upravte program tak, aby jako parametr dostal počet stěn kostky. Bude tedy umět házet třeba sedmistěnnou nebo devítistěnnou kostkou podle toho, jaké číslo dostane na vstupu.
- Předejte programu další parametr, který bude udávat kolik hodů má program provést. Program pak na výstup vytiskne seznam tolika hodů, kolik jste zadali na vstupu. Cílem je tedy vymyslet, jak vyrobit seznam náhodných čísel.

### Řešení

Ukážeme si rovnou třetí bod 

```python
import sys
import random

pocet_sten = int(sys.argv[1])
pocet_hodu = int(sys.argv[2])

hody = [random.randint(1, pocet_sten) for _ in range(pocet_hodu)]

print(hody)
```

