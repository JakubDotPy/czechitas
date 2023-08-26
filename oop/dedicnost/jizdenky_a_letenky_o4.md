## Jízdenky a letenky ◇◆◆◆◆

Nyní je naším cílem práce pro společnost, která se zabývá prodejem jízdenek a letenek.

- Vytvoř třídu `Ticket`, která bude mít atributy `basic_price` (základní cena) a `seat_number` (číslo sededla). Tato
  třída bude sloužit například pro cesty autobusem.
- Při cestování vlakem musíme řešit, jestli cestující využívá 1. nebo 2. třídu. Vytvoř třídu `TrainTicket`, která bude
  mít navíc atribut `fare_class` (uvažujeme možnosti `economy` a `business`). Dále naprogramuj metodu `get_price()`,
  která bude vracet hodnotu stejnou jako `basic_price`, pokud atribut `fare_class` je `economy`, a cenu o 20 % vyšší
  oproti `basic_price`, pokud `fare_class` je `business`.
- U letenek řešíme třídu, kterou cestující letí, navíc ale musíme řešit i počet odbavených zavazadel. Vytvoř
  třídu `PlaneTicket`, která bude dědit od třídy `TrainTicket` a bude mít navíc atribut `checkout_luggages`, který udává
  počet odbavených zavazadel. Naprogramuj metodu `get_price()`, která bude vracet hodnotu stejnou jako `basic_price`,
  pokud atribut `fare_class` je `economy`, a cenu o 50 % vyšší oproti `basic_price`, pokud `fare_class` je `business`.
  Dále připočti 2000 za každé odbavené zavazadlo (bez ohledu na třídu).
- Vytvoř jízdenku na vlak se základní cenou 150 do tříd `economy` i `business`. Zkontroluj, jakou hodnotu vrací
  metoda `get_price()`.
- Vytvoř letenku se základní cenou 6000 do tříd `economy` i `business` s jedním odbaveným zavazadlem. Zkontroluj, jakou
  hodnotu vrací metoda `get_price()`.

<details>
<summary><b>Řešení</b></summary>


```python
class Ticket:
    def __init__(self, basic_price, seat_number):
        self.basic_price = basic_price
        self.seat_number = seat_number


class TrainTicket(Ticket):
    def __init__(self, basic_price, seat_number, fare_class):
        super().__init__(basic_price, seat_number)
        self.fare_class = fare_class

    def get_price(self):
        if self.fare_class == 'economy':
            return self.basic_price
        elif self.fare_class == 'business':
            return self.basic_price * 1.2


class PlaneTicket(TrainTicket):
    def __init__(self, basic_price, seat_number, fare_class, checkout_luggages):
        super().__init__(basic_price, seat_number, fare_class)
        self.checkout_luggages = checkout_luggages

    def get_price(self):
        luggage_price = self.checkout_luggages * 2000
        if self.fare_class == 'economy':
            return self.basic_price + luggage_price
        elif self.fare_class == 'business':
            return self.basic_price * 1.5 + luggage_price


# Testování:
train_ticket_economy = TrainTicket(150, '1A', 'economy')
train_ticket_business = TrainTicket(150, '1A', 'business')
print(train_ticket_economy.get_price())  # 150
print(train_ticket_business.get_price())  # 180

plane_ticket_economy = PlaneTicket(6000, '15B', 'economy', 1)
plane_ticket_business = PlaneTicket(6000, '15B', 'business', 1)
print(plane_ticket_economy.get_price())  # 8000
print(plane_ticket_business.get_price())  # 11000
```

</details>
