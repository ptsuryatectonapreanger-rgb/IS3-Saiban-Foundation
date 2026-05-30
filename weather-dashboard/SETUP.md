# Weather Dashboard - Setup Guide

## Prerequisites
- Node.js 16+ & npm 8+
- Browser with geolocation support
- OpenWeatherMap API key

## Quick Start

### 1. Get API Key
1. Visit [OpenWeatherMap API](https://openweathermap.org/api)
2. Sign up for a free account
3. Go to API keys section
4. Copy your API key

### 2. Setup Project
```bash
cd weather-dashboard
npm install
```

### 3. Configure Environment
Create `.env.local`:
```bash
cp .env.example .env.local
```

Edit `.env.local`:
```env
NEXT_PUBLIC_WEATHER_API_KEY=your_api_key_here
NEXT_PUBLIC_WEATHER_API_URL=https://api.openweathermap.org/data/2.5
```

### 4. Run Development Server
```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

## Features

### Current Weather Display
- Real-time temperature and conditions
- Feels like temperature
- Min/Max temperatures
- Wind speed and direction
- Humidity level
- Visibility
- Pressure
- Cloud coverage
- Sunrise/Sunset times

### 5-Day Forecast
- Daily forecasts with emoji icons
- 24-hour hourly breakdown
- Temperature trends
- Precipitation probability
- Weather conditions

### User Experience
- 🔍 Search by city name
- 📍 Auto-detect location with geolocation
- 🌡️ Toggle between Celsius/Fahrenheit
- 📱 Fully responsive design
- 🎨 Light/Dark mode support
- ⚡ Real-time data updates

## API Endpoints

### Current Weather
```
GET /weather?q={city}&appid={API_KEY}&units=metric
```

### 5-Day Forecast
```
GET /forecast?q={city}&appid={API_KEY}&units=metric&cnt=40
```

### By Coordinates
```
GET /weather?lat={lat}&lon={lon}&appid={API_KEY}&units=metric
GET /forecast?lat={lat}&lon={lon}&appid={API_KEY}&units=metric
```

## Project Structure
```
weather-dashboard/
├── app/
│   ├── layout.tsx          # Root layout
│   ├── page.tsx            # Main dashboard page
│   └── globals.css         # Global styles
├── components/
│   ├── SearchBar.tsx       # City search component
│   ├── WeatherCard.tsx     # Current weather display
│   ├── Forecast.tsx        # Forecast display
│   ├── LoadingSpinner.tsx  # Loading state
│   └── ErrorAlert.tsx      # Error messages
├── lib/
│   ├── weatherAPI.ts       # API calls
│   ├── weatherStore.ts     # Zustand store
│   ├── constants.ts        # Constants & config
│   └── utils.ts            # Utility functions
├── types/
│   └── weather.ts          # TypeScript types
├── public/                 # Static files
├── .env.example            # Environment template
├── next.config.js          # Next.js config
├── tailwind.config.ts      # Tailwind config
├── tsconfig.json           # TypeScript config
└── package.json
```

## Key Technologies

### Frontend Framework
- **Next.js 14** - React framework
- **React 18** - UI library
- **TypeScript** - Type safety

### Styling
- **Tailwind CSS** - Utility CSS
- **Dark Mode** - Built-in support

### State Management
- **Zustand** - Lightweight state manager
- **LocalStorage** - Persist user preferences

### HTTP Client
- **Axios** - API requests

### Icons
- **React Icons** - Icon library

## Development Commands

```bash
# Start development server
npm run dev

# Build for production
npm run build

# Start production server
npm run start

# Lint code
npm run lint
```

## Environment Variables
- `NEXT_PUBLIC_WEATHER_API_KEY` - OpenWeatherMap API key (required)
- `NEXT_PUBLIC_WEATHER_API_URL` - API base URL (default: https://api.openweathermap.org/data/2.5)

## Troubleshooting

### API Key Issues
- Verify API key is correct and active
- Check free tier rate limits (1000 calls/day)
- Wait a few minutes after creating key before using

### Geolocation Not Working
- Check browser permissions for location access
- Ensure HTTPS or localhost (geolocation requires secure context)
- Try manual search instead

### No Weather Data Showing
- Check browser console for errors
- Verify network tab shows successful API calls
- Ensure `.env.local` is properly configured

### Build Errors
```bash
# Clear cache and reinstall
rm -rf .next node_modules package-lock.json
npm install
npm run build
```

## Deployment

### Vercel (Recommended)
```bash
# Install Vercel CLI
npm i -g vercel

# Deploy
vercel
```

Then add environment variables in Vercel dashboard.

### Other Platforms
1. Build: `npm run build`
2. Set environment variables
3. Start: `npm run start`

## Performance Tips
- API responses are cached in localStorage
- Debounce search input to reduce API calls
- Use pagination for large datasets
- Optimize images with Next.js Image component

## Security
- API key is public (NEXT_PUBLIC_*) - OpenWeatherMap allows this
- HTTPS recommended for production
- Never commit `.env.local` file
- Use `.env.example` for templates

## Future Enhancements
- Weather alerts & notifications
- Multiple location favorites
- Historical weather data
- Weather maps integration
- Air quality index
- UV index
- Pollen forecast
- Weather comparison tools
- Export weather reports
- Mobile app version

## Resources
- [OpenWeatherMap Documentation](https://openweathermap.org/api)
- [Next.js Documentation](https://nextjs.org/docs)
- [React Documentation](https://react.dev)
- [Tailwind CSS Docs](https://tailwindcss.com/docs)
- [Zustand Documentation](https://github.com/pmndrs/zustand)

## License
MIT - Feel free to use this project for any purpose.

## Support
For issues or questions:
1. Check OpenWeatherMap API docs
2. Review troubleshooting section
3. Check browser console for errors
4. Try with a different city name
