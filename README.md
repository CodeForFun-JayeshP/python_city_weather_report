# python_city_weather_report
the is python program which gives you detail of weather report of location you type.

import requests
from datetime import datetime

my_Api = "b3168d2f0e68cfdd2aa6e6edbe2da57c" #here you can use your API 
city = (input("Enter the name of city: ")).upper()  

link = "https://api.openweathermap.org/data/2.5/weather?q="+city+"&appid="+my_Api  #this is link of from where you will get weather report
api = requests.get(link)
data = api.json()
temperature = ((data["main"]["temp"])-273)
weather_cond = data["weather"][0]["description"]
Humidity = data["main"]["humidity"]
Wind_speed = data["wind"]["speed"
t_and_d = datetime.now().strftime("%d %b %Y || %I:%M:%S %p ")
print(f"Enter city name : {city}")
print("----------------------------------------------------------------")
print(f"Weather Status - {city}  || {t_and_d} ")
print("----------------------------------------------------------------")
print(f"Current temperature is : {round(temperature)}\N{DEGREE SIGN}C \nCurrent weather descr  : {weather_cond} "
      f"\nCurrent Humidity       : {Humidity}% \nCurrent wind speed     : {Wind_speed} kmph ")
print("================================================================")
