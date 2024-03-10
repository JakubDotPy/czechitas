## Booking

Stáhni si data ze souboru o rezervacích hotelů ze serveru Booking.com. Data jsou uložená v
souboru [hotel_bookings.csv](https://kodim.cz/cms/assets/czechitas/python-data-1/python-pro-data-1/pivot-tabulky/dalsi-funkce/booking/hotel_bookings.csv).
U rezervací evidujeme, jestli byly zrušené, to najdeme ve sloupci `is_canceled` (1 pro zrušené rezervace a 0 pro
nezrušené). Vytvoř kontingenční tabulku, která porovná počet zrušených rezervací podle typu hotelu (sloupec `hotel`). 
Je více rezervací zrušeno pro městské hotely nebo pro hotely v rezortech?

Dále zkus rezervace rozdělit do skupin podle toho, v jakém předstihu byly rezervace provedeny. Zaměř se pouze na
rezervace v městkých hotelech, tj. vytvoř tabulku, která bude obsahovat pouze data, které mají ve sloupci `hotel`
hodnotu `City Hotel`- Využij sloupec `lead_time`. Níže máš skupiny, podle kterých můžeš data rozdělit. Vytvoř si pivot
tabulku, která zobrazuje počty rezervací v jednotlivých kategoriích v závislosti na tom, jestli byly zrušeny nebo ne.
Pro které kategorie je více zrušených rezervací a pro které naopak více nezrušených? A v jaké skupině je celkově nejvíce
rezervací?

| Lead Time | Reservation Category |
|-----------|----------------------|
| 0-7       | Last-minute          |
| 8-30      | Short-term           |
| 31-180    | Medium-term          |
| 180-inf   | Long-term            |

<details>
<summary><b>Řešení</b></summary>

```python
# TODO: add solution
```

</details>