## Fahrnheit vs. celsius

Pokud pečete podle anglických receptů, často se po váš požaduje rozehřát troubu na uvedenou teplotu. Pokud si ovšem
neuvědomíte, že Američané používají pro měření teploty stupně Fahrenheita namísto Celsia, bude vás na konci pečení čekat
nemilé překvapení.

Nastudujte si na [České Wikipedii](https://cs.wikipedia.org/wiki/Stupe%C5%88_Fahrenheita) jak se převádějí stupně
Fahrenheita na stupně Celsia a napište program, který takový převod provede. Váš program se zeptá uživatele na teplotu
ve stupních Fahrenheita a vypíše její ekvivalent ve stupních Celsia.


<details>
<summary><b>Řešení</b></summary>

```python
fahrenheit = float(input('Zadej teplotu ve stupních Fahrenheit: '))
celsius = (fahrenheit - 32) / (9 / 5)
print(f'{fahrenheit}°F je {celsius:.2f}°C')
```

</details>