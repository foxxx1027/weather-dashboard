# 🌤️ Weather Dashboard

A full-stack weather dashboard application that fetches real-time weather data from OpenWeatherMap API. Built with React (frontend) and Express.js (backend).

## Features

✨ **Key Features**:
- 🔍 Search weather for any city worldwide
- 🌡️ Display current weather conditions (temperature, humidity, pressure, wind speed)
- 📅 5-day weather forecast
- 📱 Responsive design with Tailwind CSS
- 🎨 Beautiful gradient UI with glassmorphism effects
- ⚡ Fast and lightweight

## Tech Stack

**Frontend:**
- React 18
- Tailwind CSS
- Axios (HTTP client)

**Backend:**
- Node.js
- Express.js
- Axios (API requests)
- CORS (Cross-Origin Resource Sharing)

**API:**
- OpenWeatherMap API

## Project Structure

```
weather-dashboard/
├── server/                 # Backend Express server
│   ├── index.js           # Main server file
│   └── package.json       # Backend dependencies
├── client/                # Frontend React app
│   ├── public/
│   │   └── index.html     # HTML template
│   ├── src/
│   │   ├── components/    # React components
│   │   ├── utils/         # Utility functions
│   │   ├── App.js         # Main app component
│   │   └── index.js       # React entry point
│   ├── tailwind.config.js # Tailwind configuration
│   └── package.json       # Frontend dependencies
├── .env.example           # Environment variables template
├── .gitignore            # Git ignore rules
└── package.json          # Root package.json
```

## Prerequisites

- Node.js (v14 or higher)
- npm or yarn
- OpenWeatherMap API key (get free one at https://openweathermap.org/api)

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/foxxx1027/weather-dashboard.git
cd weather-dashboard
```

### 2. Install all dependencies

```bash
npm run install-all
```

This will install dependencies for the root, server, and client directories.

### 3. Set up environment variables

Create a `.env` file in the root directory based on `.env.example`:

```bash
cp .env.example .env
```

Then edit `.env` and add your OpenWeatherMap API key:

```
REACT_APP_API_URL=http://localhost:5000/api
PORT=5000
OPENWEATHER_API_KEY=your_api_key_here
NODE_ENV=development
```

### 4. Get your OpenWeatherMap API Key

1. Visit https://openweathermap.org/api
2. Sign up for a free account
3. Go to your API keys page
4. Copy your API key and paste it in the `.env` file

## Running the Application

### Development Mode (Both Frontend & Backend)

Run from the root directory:

```bash
npm run dev
```

This will start:
- **Backend Server**: Running on http://localhost:5000
- **Frontend App**: Running on http://localhost:3000

### Or Run Separately

**Backend only:**
```bash
npm run server
```

**Frontend only:**
```bash
npm run client
```

## API Endpoints

### Backend API (http://localhost:5000/api)

| Endpoint | Method | Parameters | Description |
|----------|--------|-----------|-------------|
| `/health` | GET | - | Health check |
| `/weather/current` | GET | `city` | Get current weather by city name |
| `/weather/forecast` | GET | `city` | Get 5-day forecast by city name |
| `/weather/coordinates` | GET | `lat`, `lon` | Get current weather by coordinates |

### Example Requests

```bash
# Get current weather for London
curl "http://localhost:5000/api/weather/current?city=London"

# Get forecast for New York
curl "http://localhost:5000/api/weather/forecast?city=New%20York"

# Get weather by coordinates
curl "http://localhost:5000/api/weather/coordinates?lat=51.5074&lon=-0.1278"
```

## Usage

1. Open http://localhost:3000 in your browser
2. Enter a city name in the search bar
3. Click "Search" to fetch weather data
4. View current weather and 5-day forecast

## Features Explained

### Current Weather Display
- City name and country code
- Current temperature (feels like, min/max)
- Weather description
- Weather icon
- Humidity percentage
- Pressure (hPa)
- Wind speed (m/s)
- Visibility (km)

### 5-Day Forecast
- Daily weather icon
- Temperature
- Weather condition
- Humidity percentage
- Date and day of week

## Customization

### Change Default City
Edit `client/src/App.js`:
```javascript
const [city, setCity] = useState('London'); // Change 'London' to your preferred city
```

### Modify Styling
All styles use Tailwind CSS. Customize colors and styles in:
- `client/src/index.css` - Global styles
- `client/tailwind.config.js` - Tailwind configuration
- Individual component files - Component-specific styles

### Add More Features
- Temperature unit toggle (Celsius/Fahrenheit)
- Save favorite cities
- Location-based weather (geolocation)
- Weather alerts
- Air quality index

## Troubleshooting

### "API key not configured"
- Make sure you've added your OpenWeatherMap API key to the `.env` file
- Restart the backend server after updating `.env`

### CORS errors
- Make sure the backend is running on http://localhost:5000
- Check that `REACT_APP_API_URL` is set correctly in the frontend

### "City not found"
- Make sure the city name is spelled correctly
- Try searching for major cities first
- Some small towns might not be available in the API

### Port already in use
- Backend default port: 5000
- Frontend default port: 3000
- You can change these in the `.env` file and server configuration

## Performance Tips

- The app caches weather data during the session
- API calls are minimized through proper state management
- Images and icons are emoji-based for lightweight loading

## Security Notes

- Never commit your `.env` file with real API keys
- Keep your API key private and rotate it periodically
- Consider using environment variables in production
- Rate limit your API calls if deploying publicly

## License

MIT

## Support

For issues or questions:
1. Check the troubleshooting section
2. Review OpenWeatherMap API documentation
3. Open an issue on GitHub

## Future Enhancements

- [ ] Weather alerts and notifications
- [ ] Historical weather data
- [ ] Multiple location tracking
- [ ] Weather maps integration
- [ ] Air quality index
- [ ] UV index
- [ ] Pollen data
- [ ] Severe weather warnings

---

**Enjoy using Weather Dashboard!** 🌤️
