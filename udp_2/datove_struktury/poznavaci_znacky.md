## Poznávací značky

V následujícím slovníků je evidence automobilů. Klíčem jsou státní poznávací značky (SPZ) a hodnotou je jméno majitele
vozu.

```python
spzetky = {
    "4A2 3000": "František Novák",
    "6P5 4747": "Jana Pilná",
    "3B7 3652": "Jaroslav Sečkár",
    "1P5 5269": "Marta Nováková",
    "37E 1252": "Martina Matušková",
    "2A5 2241": "Jan Král"
}
```

- Napiš program, který vypíše všechny majitele, jejichž vozidlo je registrováno v Plzeňském kraji.  
  tj. na druhém místě (index 1) řetězce v klíči je písmeno P.

<details>
<summary><b>Řešení</b></summary>

```python
print('Lidé z Plzeňského kraje:')
for spz, jmeno in spzetky.items():
    if spz[1] == 'P':
        print(f'- {jmeno}')
```

</details>
