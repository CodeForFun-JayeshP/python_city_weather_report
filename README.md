# python_city_weather_report
the is python program which gives you detail of weather report of location you type.

import requests<br/>
from datetime import datetime

my_Api = "b3168d2f0e68cfdd2aa6e6edbe2da57c"<br/> #you can your here your own API
city = (input("Enter the name of city: ")).upper()<br/>

link = "https://api.openweathermap.org/data/2.5/weather?q="+city+"&appid="+my_Api<br/>
api = requests.get(link)<br/>
data = api.json()<br/>
temperature = ((data["main"]["temp"])-273)<br/>
weather_cond = data["weather"][0]["description"]<br/>
Humidity = data["main"]["humidity"]<br/>
Wind_speed = data["wind"]["speed"<br/>
t_and_d = datetime.now().strftime("%d %b %Y || %I:%M:%S %p ")<br/>
print(f"Enter city name : {city}")<br/>
print("----------------------------------------------------------------")<br/>
print(f"Weather Status - {city}  || {t_and_d} ")<br/>
print("----------------------------------------------------------------")<br/>
print(f"Current temperature is : {round(temperature)}\N{DEGREE SIGN}C \nCurrent weather descr  : {weather_cond} "
      f"\nCurrent Humidity       : {Humidity}% \nCurrent wind speed     : {Wind_speed} kmph ")<br/>
print("================================================================")<br/>
