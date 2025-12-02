#  Basic Weather App

**A beautifully formatted command-line weather application** that fetches real-time weather data using OpenWeatherMap API with emoji-rich visual displays.

##  Features

| Category | Features |
|----------|----------|
| **📍 Location** | City search, ZIP code, International support |
| **🌡️ Units** | Celsius/Fahrenheit toggle |
| **📊 Data** | Temp, humidity, wind, visibility, sunrise/sunset |
| **🎨 Display** | Emoji icons, formatted tables, color-coded output |
| **🛡️ Reliability** | Error handling, input validation, demo mode |

##  Quick Start

### 1. **Install Dependencies**
```bash
pip install requests
```

### 2. **Get Your API Key**
1. Go to [OpenWeatherMap](https://openweathermap.org/api)
2. Create free account
3. Copy 32-character API key

### 3. **Configure Application**
In `weather_app.py`, replace:
```python
API_KEY = "YOUR_API_KEY_HERE"  # Line 267
```
With your actual key:
```python
API_KEY = "your_32_char_api_key_here"
```

### 4. **Run the Application**
```bash
python weather_app.py
```

##  How to Use

### **Basic Navigation**
```
🌤️  BASIC WEATHER APPLICATION 🌤️
1. Check weather by location
2. Change temperature units
3. Exit
Enter your choice (1-3): 1
```

### **Search Examples**
| Input Type | What to Type | Example |
|------------|--------------|---------|
| City | City name | `London` |
| City + Country | City, Country | `Paris, FR` |
| US ZIP | 5-digit code | `90210` |
| Intl ZIP | Code + Country | `75001, FR` |

##  Sample Output
```
==================================================
WEATHER FORECAST - London, GB
==================================================

🌤️  Current Conditions: Cloudy
🌡️  Temperature: 12°C (Feels like: 10°C)
💧 Humidity: 85%
📊 Pressure: 1015 hPa
💨 Wind Speed: 6.2 m/s
🧭 Wind Direction: W (270°)
👁️  Visibility: 10000 meters
🌅 Sunrise: 07:45:00
🌇 Sunset: 16:30:00
--------------------------------------
Additional Details:
Weather Icon: ☁️
☁️  Cloud Coverage: 90%
==================================================
```

##  Supported Weather Icons

| Condition | Icon | Description |
|-----------|------|-------------|
| Clear | ☀️ | Sunny weather |
| Clouds | ☁️ | Cloudy skies |
| Rain | 🌧️ | Rainfall |
| Snow | ❄️ | Snowfall |
| Thunderstorm | ⛈️ | Storms |
| Mist/Haze | 🌫️ | Low visibility |

##  Quick Commands Cheat Sheet

```bash
# Run application
python weather_app.py

# Test API key (replace YOUR_KEY)
python -c "import requests; r=requests.get('http://api.openweathermap.org/data/2.5/weather?q=London&appid=YOUR_KEY'); print('✅ Working' if r.status_code==200 else '❌ Check key')"

# Common inputs to try
1 → London          # London weather
1 → Tokyo           # Tokyo weather  
1 → 90210 → Enter   # Beverly Hills, CA
2 → 2               # Switch to Fahrenheit
```

##  Troubleshooting

| Problem | Solution |
|---------|----------|
| **API Key Invalid** | Wait 10-15 minutes after creation |
| **City Not Found** | Add country code: `London,UK` |
| **No Output** | Ensure Python 3.11+ and internet connection |
| **ZIP Code Error** | Specify country: `400001,IN` |
| **Demo Mode** | Type `yes` when prompted |

##  Project Structure
```
weather_app.py
├── WeatherApp Class
│   ├── get_weather_by_city()    # Fetch by city
│   ├── get_weather_by_zip()     # Fetch by ZIP
│   ├── display_weather()        # Format output
│   ├── set_units()              # C° ↔ F°
│   └── validate_input()         # Input validation
├── main()                       # Entry point
└── display_demo_weather()       # Fallback mode
```

##  Requirements
- **Python**: 3.11.9 or higher
- **Library**: `requests` only
- **API**: OpenWeatherMap free account
- **Internet**: Required for live data

##  API Information
- **Service**: OpenWeatherMap Current Weather API
- **Endpoint**: `api.openweathermap.org/data/2.5/weather`
- **Rate Limit**: 60 calls/minute (free)
- **Format**: JSON response
- **Authentication**: API key required
