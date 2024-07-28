## Čísla v textu

Máme obdobné zadání jako v předchozím cvičení, avšak tentokrát máme čísla zadána nikoliv v seznamu, ale v řetězci
oddělená mezerou:

```python
hodnoty = '12.1 1.68 7.45 -11.51'
```

K poslednímu číslu v seznamu chceme přičíst `0.25` tak, aby výsledek vypadal takto

```python
hodnoty = '12.1 1.68 7.45 -11.26'
```

Určitě se vám budou hodit metody `split` a `join`.

<details>
<summary><b>Řešení</b></summary>


```python
hodnoty = '12.1 1.68 7.45 -11.51'
hodnoty_list = hodnoty.split()

posledni = hodnoty_list[-1]
prepocteno = float(posledni) + 0.25
hodnoty_list[-1] = str(prepocteno)

hodnoty = ' '.join(hodnoty_list)
```

</details>
