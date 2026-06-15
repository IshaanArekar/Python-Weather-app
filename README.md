**Weather App**

A simple desktop weather application built with Python and PyQt5. Enter a city name and get the current temperature, a weather condition emoji, and a short description, pulled live from the OpenWeatherMap API.

**Features:**

- Clean PyQt5 graphical interface
- Live current weather data from the OpenWeatherMap API
- Temperature displayed in Fahrenheit
- Weather condition shown as an emoji (clear, clouds, rain, snow, thunderstorm, fog, and more)
- Friendly error messages for bad input, network issues, and API errors (400, 401, 403, 404, 500, 502, 503, 504)
- API key kept out of the source code using a `.env` file

**Requirements:**

- Python 3.10 or newer (the code uses `match` statements)
- An OpenWeatherMap API key (free tier works)

**Installation:**

1. Clone the repository:

   
   git clone [[https://github.com/yourusername/weather-app.git](https://github.com/IshaanArekar/Python-Weather-app.git)]
   cd weather-app
   
2. Install the dependencies:
 
   pip install PyQt5 requests python-dotenv
   

**Setup:**

1. Create a free account at [OpenWeatherMap](https://openweathermap.org/api) and generate an API key.

2. Create a file named `.env` in the project root (the same folder as `main.py`) and add your key:

   ```
   api_key=your_api_key_here
   ```

   Do not wrap the key in quotes and do not put spaces around the equals sign.

3. Note that a brand new OpenWeatherMap key can take up to a couple of hours to activate. Until it does, every request returns a 401 error even though the key is correct.

**Usage:**

Run the app:

python3 main.py


Type a city name into the input box and click **Get Weather**.

**How It Works: **

The app sends a request to the OpenWeatherMap current weather endpoint:

```
https://api.openweathermap.org/data/2.5/weather?q={city}&appid={api_key}
```

The response includes a numeric weather condition code, which the app maps to an emoji, along with the temperature and a text description. Network and HTTP errors are caught and shown to the user as readable messages rather than crashing the app.

