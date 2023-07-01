# the-Binance-API-to-fetch-real-time-price-data-for-a-specific-cryptocurrency-pair
This script uses the Binance API to fetch real-time price data for a specific cryptocurrency pair
import requests

def get_crypto_price(pair):
    url = f'https://api.binance.com/api/v3/ticker/price?symbol={pair}'
    response = requests.get(url)
    data = response.json()
    if 'price' in data:
        return float(data['price'])
    return None

# Example usage
crypto_pair = 'BTCUSDT'

price = get_crypto_price(crypto_pair)
if price:
    print(f"Current price of {crypto_pair}: ${price}")
else:
    print(f"Failed to retrieve price for {crypto_pair}")
