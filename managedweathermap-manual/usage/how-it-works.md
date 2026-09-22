---
description: How does it work?
---

# ⚒️ How it works

This library has two separate functions:

* `GetWeatherInfo()`
* `ListAllCities()`

## Getting weather information

Using `GetWeatherInfo()`, you can supply one of the following:

* `CityID` and `APIKey`
* `CityName` and `APIKey`
* `WeatherURL` (which is a custom URL to OpenWeatherMap API with the API key supplied within)

To get relevant information, ManagedWeatherMap downloads the URL as a string and the JSON parser attempts to parse the resulting weather data.

After this happens, the processing of information begins by saving the values to the new instance of the `ForecastInfo` class and returns it.

## Listing cities

If you want to list all the cities available for getting the weather information, you can call the `ListAllCities()` function which returns a `Dictionary<long, string>`, which:

* `long`: City ID
* `string`: City name

First, it attempts to download the compressed city list consisting of all the available cities from around the world from [this link](http://bulk.openweathermap.org/sample/city.list.json.gz).

Then, the resuling file is decompressed into memory. After the decompression, the JSON parser attempts to parse the result. ManagedWeatherMap then iterates through each city and installs its ID and its name to the dictionary.

After this is done, it returns the dictionary.
