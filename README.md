# Weather-API-Dashboard

![Weather Dashboard](weather%20api.png)

A simple weather dashboard built with p5.js that pulls real-time weather data from the OpenWeatherMap API and displays it on a clean canvas interface.

---

## Features

- Real-time weather data via OpenWeatherMap API
- Displays temperature (Fahrenheit), humidity, and city name
- Weather description logged to console
- Minimal, easy-to-read interface
- Simple to configure for any city

---

## Screenshots

**Dashboard output:**

![Dashboard Preview](weather%20api.png)

**Code and live preview in p5.js editor:**

![p5.js Editor](weather%20api%202.png)

---

## Prerequisites

- A web browser with JavaScript enabled
- A free [OpenWeatherMap](https://openweathermap.org) API key
- p5.js (loaded via CDN, no install needed)

---

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/yourusername/weather-api-dashboard.git
cd weather-api-dashboard
```

### 2. Get an API key

Sign up at [openweathermap.org](https://openweathermap.org), navigate to the API keys section, and copy your key.

### 3. Add your API key

Open `sketch.js` and replace the placeholder:

```javascript
const apiKey = 'YOUR_API_KEY_HERE';
```

### 4. Run the app

Open `index.html` directly in your browser, or use a local server:

```bash
python -m http.server 8000
# Navigate to http://localhost:8000
```

---

## Usage

### Changing the city

Edit the `city` variable in `sketch.js`:

```javascript
const city = 'London';       // City name
const city = 'London,UK';    // City + country code
const city = 'Austin,TX,US'; // City + state + country
```

### Changing temperature units

```javascript
units=imperial   // Fahrenheit
units=metric     // Celsius
units=standard   // Kelvin
```

---

## File Structure

```
weather-api-dashboard/
├── index.html      # Main HTML file
├── sketch.js       # p5.js weather dashboard code
├── .gitignore      # Excludes API key files
├── README.md       # This file
└── LICENSE
```

---

## API Response Structure

```json
{
  "name": "New York",
  "main": {
    "temp": 72,
    "humidity": 65,
    "feels_like": 70
  },
  "weather": [
    { "description": "clear sky" }
  ],
  "wind": {
    "speed": 5.5
  }
}
```

---

## Security — Protecting Your API Key

Keep your API key out of version control by using a separate config file:

**config.js**
```javascript
const API_KEY = 'your_api_key_here';
```

**sketch.js**
```javascript
const apiKey = API_KEY;
```

Add `config.js` to your `.gitignore`:

```
config.js
.env
node_modules/
```

---

## Troubleshooting

- **API key not working** — Keys can take a few minutes to activate after signup. Free tier allows 60 calls/minute.
- **City not found** — Check spelling or add a country code (e.g. `London,UK`).
- **CORS errors** — Open via a local server rather than directly from the file system.
- **Data not displaying** — Check the browser console (F12) for errors and verify `preload()` is completing before `draw()`.

---

## License

MIT License — see the `LICENSE` file for details.

---

## Disclaimer

This project is for educational purposes. Keep your API key private and never commit it to a public repository.
