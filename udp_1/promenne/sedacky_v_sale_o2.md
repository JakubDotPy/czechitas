## Sedačky v sále

Hlavní sál divadla má k dispozici 350 sedaček. Lze je poskládat do řad po 32 sedadlech tak, aby všechny řady byly úplné?
Pokud ne, kolik sedaček musíme přikoupit, aby to šlo? Kolik nám takto vznikne celkem řad?

<details>
<summary><b>Řešení</b></summary>


```python
zbyva = 350 % 32
dokoupit = 32 - zbyva
celkem_rad = (350 + dokoupit) / 32
```

</details>
