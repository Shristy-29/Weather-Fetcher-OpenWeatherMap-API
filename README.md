# Weather-Fetcher-OpenWeatherMap-API
This Python script fetches the current weather of any city using the OpenWeatherMap API.

import requests

city_name = 'Allahabad'
API_key = input("Enter your API key")
url = f'https://api.openweathermap.org/data/2.5/weather?q={city_name}&appid={API_key}&units=metric'

response = requests.get(url)

if response.status_code == 200:
    data = response.json()
    print('City : ', data['name'])
    print('Weather : ', data['weather'][0]['description'])
    print('Tempreature : ', data['main']['temp'], 'C')
    print('Humidity : ', data['main']['humidity'])
    print('Visibility : ', data['visibility'])
