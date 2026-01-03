# Weather-API-Dashboard
A simple weather dashboard built with p5.js that displays real-time weather information using the OpenWeatherMap API.

Features

Real-time weather data from OpenWeatherMap API
Displays current temperature in Fahrenheit
Shows humidity percentage
City name display
Weather description logging
Clean, minimalist interface
Easy to customize for different cities

Demo
Current implementation shows weather for New York City with:

Temperature in Fahrenheit
Humidity percentage
City name
Weather description (console logged)

Prerequisites

Web browser with JavaScript enabled
OpenWeatherMap API key (free tier available)
p5.js library

Installation
1. Clone the repository
bashgit clone https://github.com/yourusername/weather-api-dashboard.git
cd weather-api-dashboard
2. Get an API Key

Visit OpenWeatherMap
Sign up for a free account
Navigate to API keys section
Copy your API key

3. Configure the API Key
Open sketch.js and replace the API key:
javascriptconst apiKey = 'YOUR_API_KEY_HERE';

4. Run the application
Open index.html in your web browser, or use a local server:
bash# Using Python
python -m http.server 8000

# Using Node.js
npx http-server

# Then navigate to http://localhost:8000
Usage
Changing the City
Edit the city variable in sketch.js:
javascriptconst city = 'London';  // Change to any city name
Supported formats:

City name: 'New York'
City, Country: 'London,UK'
City, State, Country: 'Austin,TX,US'

Temperature Units
Change units in the API URL:
javascript// Fahrenheit (default)
units=imperial

// Celsius
units=metric

// Kelvin
units=standard
File Structure
weather-api-dashboard/
│
├── index.html          # Main HTML file
├── sketch.js           # p5.js weather dashboard code
├── .gitignore          # Git ignore file (includes API key protection)
├── README.md           # This file
└── LICENSE             # License file
Code Overview
Main Components
Variables:
javascriptconst apiKey = 'YOUR_API_KEY';      // OpenWeatherMap API key
const city = 'New York';            // Target city
let temp = 0;                       // Temperature storage
let cityName = '';                  // City name from API
let description = '';               // Weather description
let humidity = 0;                   // Humidity percentage
Functions:

preload() - Fetches weather data before setup
setup() - Initializes canvas and text alignment
draw() - Renders weather information on canvas

API Request
javascriptlet url = `https://api.openweathermap.org/data/2.5/weather?q=${city}&units=imperial&appid=${apiKey}`;
Parameters:

q - City name
units - Temperature unit (imperial/metric/standard)
appid - Your API key

Customization
Canvas Size
javascriptcreateCanvas(400, 200);  // Change width and height
Text Styling
javascripttextSize(32);           // Adjust text size
fill(0);                // Change text color (RGB)
Background Color
javascriptbackground(240);        // Change background (0-255 or RGB)
Display Additional Data
Add more weather information from the API response:
javascriptlet windSpeed = data.wind.speed;
let pressure = data.main.pressure;
let feelsLike = data.main.feels_like;

// Display in draw()
text('Wind: ' + windSpeed + ' mph', width/2, yPosition);
API Response Structure
The OpenWeatherMap API returns data in this format:
json{
  "name": "New York",
  "main": {
    "temp": 72,
    "humidity": 65,
    "pressure": 1013,
    "feels_like": 70
  },
  "weather": [
    {
      "description": "clear sky",
      "main": "Clear"
    }
  ],
  "wind": {
    "speed": 5.5
  }
}
Security Best Practices
Protecting Your API Key

Create .gitignore file:

config.js
.env
node_modules/

Use a separate config file:

Create config.js:
javascriptconst API_KEY = 'your_api_key_here';
Update sketch.js:
javascriptconst apiKey = API_KEY;
Add config.js to .gitignore

For production, use environment variables or backend proxy

Troubleshooting
Common Issues
API key not working:

Check if key is activated (can take a few minutes)
Verify key is correctly copied
Check API call limits (60 calls/minute for free tier)

City not found:

Check spelling
Try adding country code: 'London,UK'
Use city ID instead of name

CORS errors:

Use a local server instead of opening HTML directly
Check browser console for specific errors

Data not displaying:

Open browser console (F12) to check for errors
Verify preload() completes before draw()
Check API response in Network tab

Future Enhancements

 User input field for city selection
 5-day weather forecast
 Weather icons
 Temperature unit toggle (F°/C°)
 Multiple city comparison
 Weather alerts
 Animated weather effects
 Geolocation-based weather
 Historical weather data
 Responsive design

API Documentation
Full OpenWeatherMap API documentation: https://openweathermap.org/api
Free Tier Limits

60 calls/minute
1,000,000 calls/month
Current weather data
3-hour forecast 5 days

Contributing
Contributions are welcome! Please follow these steps:

Fork the repository
Create a feature branch (git checkout -b feature/AmazingFeature)
Commit your changes (git commit -m 'Add some AmazingFeature')
Push to the branch (git push origin feature/AmazingFeature)
Open a Pull Request

License
This project is licensed under the MIT License - see the LICENSE file for details.
Acknowledgments

p5.js - Creative coding library
OpenWeatherMap - Weather API provider
Inspired by simple weather dashboard designs

Resources

p5.js Documentation
OpenWeatherMap API Guide
JavaScript Fetch API
