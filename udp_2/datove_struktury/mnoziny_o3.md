## Množiny

Následující text převeďte na množinu unikátních znaků, zjistěte počet unikátních znaků a vypište jejich seřazený seznam.

```python
text = '''Prágl
Prágl, po anglánsku Prague nebo Praha nebo v Cajsku, je taková lochna
v tem kuse hródy někde za čárama naši domoviny, kde se zoncna už
nechláme a kde se prndá po cajzlovsku. A ještě k temu tam majó sicnu
těžcí papaláši, kvůli čemu ho má každé v láfu jako kaktus ve véfuku.
Z Práglu bere kramále aj ten jejich len kerému se péruje Vltava.

O Práglu se taky kóří, pač tam majó hafo retychů pro všecky. Kromě
bůry švédských retychů só aj dva v Olmecu a jeden v Bučovicách.
To my z našeho štatlu radši hážem lulec do kašny na Zelňáku. Když
ale nekdo vopruboval zašrajbčit náš barocké Parnas do cancu retychů
pro všecky, přišmrdolili se ti Švédi s tým, že só proti a hókajó po
celé hródě, že ta vasra v tem se dá chlemtat.
'''
```

Očekávaný výstup:

```text
49
['\n', ' ', ',', '.', 'A', 'B', 'C', 'K', 'O', 'P', 'T', 'V', 'Z', 'a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'r', 's', 't', 'u', 'v', 'y', 'z', 'á', 'é', 'í', 'ó', 'ý', 'č', 'ě', 'ň', 'ř', 'Š', 'š', 'ů', 'ž']
```

<details>
<summary><b>Řešení</b></summary>


```python
unikatni = sorted(set(text))
print(len(unikatni))
print(unikatni)
```

</details>
