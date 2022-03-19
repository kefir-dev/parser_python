from requests import get
from bs4 import BeautifulSoup as bs
from fake_headers import Headers

headers = Headers().generate()

url = 'https://ligovka.ru'

res = get(url=url, headers=headers).text

soup = bs(res, 'lxml')

buy_prices = soup.find_all(class_='money_price buy_price')[0]
buy_second_price = soup.find_all(class_='money_price buy_price')[1]

for buy_price in buy_prices:
    print(f"Покупка: 1 USD -> {buy_price.text} RUB")

for buy_price in buy_second_price:
    print(f"Продажа: 1 USD -> {buy_price.text} RUB")

