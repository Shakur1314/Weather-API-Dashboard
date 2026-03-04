What it is: A weather dashboard that fetches live weather data from the OpenWeatherMap API and displays it on a canvas using p5.js.

How it works: When the page loads, preload() fires first and makes an API call to OpenWeatherMap with the city name and API key. It pulls back the temperature, humidity, city name, and weather description. Then draw() renders that data on a simple grey canvas — the city name, temperature in Fahrenheit, and humidity percentage centered on screen. The weather description (like "overcast clouds") gets printed to the console rather than displayed on canvas.

The p5.js angle: I used p5.js to handle both the data fetching and the visual rendering. preload() manages the async API call before anything loads, and draw() renders the result directly onto an HTML canvas — so instead of displaying data in plain HTML elements, it's drawn as text on a graphical canvas, which is the core of how p5.js works.

What it doesn't do yet: There's no input field, so the city is hardcoded in sketch.js. To check a different city you'd have to edit the code directly. Some things I plan to add include a city input field, forecast data, and weather icons.

Security note: The API key sits directly in sketch.js, which is fine for a personal project but would be a problem on a public repo — anyone could grab it. I documented how to move it to a separate config.js file that gets ignored by Git.

Summary: I used p5.js to call a weather API and render the response on a canvas — a straightforward introduction to working with external APIs in JavaScript.
