---
description: How do you use it?
---

# 🖥️ How to use

Using this library is very simple! Just use the `ManagedWeatherMap` namespace in any piece of code you want to use the library, as in: `using ManagedWeatherMap;`

Just use the `Forecast` class that contains:

* `GetWeatherInfo(long, string, UnitMeasurement)`
* `GetWeatherInfo(string, string, UnitMeasurement)`
* `ListAllCities()`

The first three functions download the weather information for either the specified city ID or city name and return the relevant weather information, `ForecastInfo`, that contains these properties:

* `long CityID`
* `string CityName`
* `WeatherCondition Weather`
* `UnitMeasurement TemperatureMeasurement` (see [weather conditions](https://openweathermap.org/weather-conditions))
* `double Temperature`
* `double FeelsLike`
* `double Pressure`
* `double Humidity`
* `double WindSpeed`
* `double WindDirection`

where the `UnitMeasurement` is:

* `Kelvin`
  * Measurement for `Temperature` and `FeelsLike` is `K` (Kelvin)
  * Measurement for `WindSpeed` is `m.s` (Meters per second)
  * Measurement for `Pressure` is `hPa` (Hectopascal)
* `Metric`
  * Measurement for `Temperature` and `FeelsLike` is `C` (Celsius)
  * Measurement for `WindSpeed` is `m.s` (Meters per second)
  * Measurement for `Pressure` is `hPa` (Hectopascal)
* `Imperial`
  * Measurement for `Temperature` and `FeelsLike` is `F` (Fahrenheit)
  * Measurement for `WindSpeed` is `mph` (Miles per hour)
  * Measurement for `Pressure` is `hPa` (Hectopascal)

{% hint style="warning" %}
You're required to provide the API key for each weather operation, which you can get by [visiting this page](https://home.openweathermap.org/api_keys).
{% endhint %}

### Asynchronous Operation

For web development and other cases where asynchronous development is appropriate, you can use the below functions which are declared to be asynchronous:

```csharp
public static async Task<ForecastInfo> GetWeatherInfoAsync(long CityID, string APIKey, UnitMeasurement Unit = UnitMeasurement.Metric)
public static async Task<ForecastInfo> GetWeatherInfoAsync(string CityName, string APIKey, UnitMeasurement Unit = UnitMeasurement.Metric)
public static async Task<Dictionary<long, string>> ListAllCitiesAsync()
```
