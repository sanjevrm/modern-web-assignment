# modern-web-activity
## NAME: SANJEV R M
## REG NO: 212223040186

# PROGRAM
```
app.js
import React, { useState } from "react";
import "./App.css"; // Add your CSS styles here

const WeatherApp = () => {
  const mockWeatherData = {
    London: { temperature: "15°C", windSpeed: "10 km/h", skyCondition: "Cloudy" },
    Paris: { temperature: "18°C", windSpeed: "8 km/h", skyCondition: "Sunny" },
    Tokyo: { temperature: "20°C", windSpeed: "12 km/h", skyCondition: "Rainy" },
  };

  const [city, setCity] = useState("");
  const [weather, setWeather] = useState(null);
  const [error, setError] = useState("");

  const handleSearch = () => {
    if (mockWeatherData[city]) {
      setWeather(mockWeatherData[city]);
      setError("");
    } else {
      setWeather(null);
      setError("City not found. Please try again.");
    }
  };

  const handleKeyPress = (e) => {
    if (e.key === "Enter") {
      handleSearch();
    }
  };

  return (
    <div className="weather-app">
      <h1>Weather App</h1>
      <input
        type="text"
        placeholder="Enter city name"
        value={city}
        onChange={(e) => setCity(e.target.value)}
        onKeyPress={handleKeyPress}
      />
      <button onClick={handleSearch}>Search</button>
      {weather && (
        <div className="weather-info">
          <h2>Weather in {city}</h2>
          <p>Temperature: {weather.temperature}</p>
          <p>Wind Speed: {weather.windSpeed}</p>
          <p>Sky Condition: {weather.skyCondition}</p>
        </div>
      )}
      {error && <p className="error-message">{error}</p>}
    </div>
  );
};

export default WeatherApp;
```

```
app.css
.App {
  text-align: center;
}

.App-logo {
  height: 40vmin;
  pointer-events: none;
}

@media (prefers-reduced-motion: no-preference) {
  .App-logo {
    animation: App-logo-spin infinite 20s linear;
  }
}

.App-header {
  background-color: #282c34;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  font-size: calc(10px + 2vmin);
  color: white;
}

.App-link {
  color: #61dafb;
}

@keyframes App-logo-spin {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

.weather-app {
  font-family: Arial, sans-serif;
  text-align: center;
  margin: 20px;
}

input {
  padding: 10px;
  margin: 10px;
  width: 200px;
  border: 1px solid #ccc;
  border-radius: 4px;
}

button {
  padding: 10px 20px;
  background-color: #007bff;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

button:hover {
  background-color: #0056b3;
}

.weather-info {
  margin-top: 20px;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
  display: inline-block;
  text-align: left;
}

.error-message {
  color: red;
  margin-top: 20px;
}
```

# OUTPUT
