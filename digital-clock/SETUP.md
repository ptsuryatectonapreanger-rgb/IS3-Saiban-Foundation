# Digital Clock - Setup Guide

## Quick Start

### 1. Install Dependencies
```bash
cd digital-clock
npm install
```

### 2. Run Development Server
```bash
npm run dev
```

### 3. Open Browser
Visit `http://localhost:3000`

## Features

### 🕐 Digital Clock Display
- Real-time clock showing hours, minutes, and seconds
- Current date with day of the week
- 24-hour or 12-hour format toggle
- Timezone name and abbreviation
- Beautiful gradient UI with animations

### 🕰️ Analog Clock View
- Traditional clock face with hour/minute/second hands
- Smooth hand rotations
- Red second hand
- Toggle between digital and analog display

### 🌍 Multiple Timezones
- Support for 50+ timezones worldwide
- Add/remove timezones on demand
- View multiple timezones simultaneously
- Search for timezones by city or code

### ⭐ Favorites Management
- Mark favorite timezones
- Quick access to saved locations
- Persistent storage across sessions
- Easy management with star icons

### 📊 Time Difference Calculator
- Automatic calculation of time differences
- View which timezone is ahead/behind
- Display in hours and minutes format
- Visual offset indicators

### ⚙️ Settings Panel
- Toggle 24/12 hour format
- Show/hide seconds
- Switch between digital and analog clock
- Theme selection (light/dark/auto)

### 📱 Responsive Design
- Mobile-first approach
- Tablet optimization
- Desktop-friendly layout
- Touch-optimized controls

## Supported Timezones

### Americas
- America/New_York (EST/EDT)
- America/Los_Angeles (PST/PDT)
- America/Chicago (CST/CDT)
- America/Denver (MST/MDT)
- America/Toronto (EST/EDT)
- America/Mexico_City
- America/Sao_Paulo
- America/Buenos_Aires

### Europe
- Europe/London (GMT/BST)
- Europe/Paris (CET/CEST)
- Europe/Berlin (CET/CEST)
- Europe/Madrid (CET/CEST)
- Europe/Amsterdam (CET/CEST)
- Europe/Stockholm (CET/CEST)
- Europe/Athens (EET/EEST)
- Europe/Moscow (MSK)

### Asia
- Asia/Tokyo (JST)
- Asia/Shanghai (CST)
- Asia/Hong_Kong (HKT)
- Asia/Singapore (SGT)
- Asia/Bangkok (ICT)
- Asia/Kolkata (IST)
- Asia/Dubai (GST)
- Asia/Seoul (KST)

### Australia & Pacific
- Australia/Sydney (AEDT/AEST)
- Australia/Melbourne (AEDT/AEST)
- Australia/Brisbane (AEST)
- Australia/Perth (AWST)
- Pacific/Auckland (NZDT/NZST)
- Pacific/Fiji (FJT)
- Pacific/Honolulu (HST)

### UTC & Africa
- UTC (Coordinated Universal Time)
- Africa/Cairo (EET)
- Africa/Lagos (WAT)
- Africa/Johannesburg (SAST)
- Africa/Nairobi (EAT)

## Usage Examples

### Add a Timezone
1. Click "Add Timezone" button
2. Search for city or timezone code
3. Select from results
4. Clock appears in grid

### Toggle Favorite
1. Click star icon on clock card
2. Filled star = favorite
3. Favorites persist in storage

### Change Display Format
1. Click Settings (gear icon)
2. Toggle "24-Hour Format"
3. Toggle "Show Seconds"
4. Toggle "Show Analog Clock"

### View Time Differences
- Automatically shown when 2+ timezones added
- Shows offset in hours and minutes
- Indicates which timezone is ahead

## Development Commands

```bash
# Start development server
npm run dev

# Build for production
npm run build

# Start production server
npm run start

# Run linting
npm run lint
```

## Tech Stack

- **Frontend Framework**: Next.js 14 + React 18
- **Language**: TypeScript
- **Styling**: Tailwind CSS
- **State Management**: Zustand
- **Time Libraries**: date-fns, Day.js
- **Icons**: React Icons

## File Structure

```
digital-clock/
├── app/
│   ├── page.tsx              # Main page
│   ├── layout.tsx            # Root layout
│   └── globals.css           # Global styles
├── components/
│   ├── DigitalClock.tsx      # Digital display
│   ├── AnalogClock.tsx       # Analog display
│   ├── TimezoneSelector.tsx  # Add timezone
│   ├── TimezoneDifference.tsx# Difference calc
│   └── SettingsPanel.tsx     # Settings
├── lib/
│   ├── timezoneStore.ts      # Zustand store
│   ├── timezones.ts          # Timezone data
│   └── utils.ts              # Utilities
├── types/
│   └── clock.ts              # Type definitions
├── public/                   # Static files
├── .env.example             # Environment template
├── package.json             # Dependencies
├── tsconfig.json            # TypeScript config
├── tailwind.config.ts       # Tailwind config
├── next.config.js           # Next.js config
├── postcss.config.js        # PostCSS config
└── README.md                # Documentation
```

## Performance Features

- ✅ Efficient time updates (1 second interval)
- ✅ Debounced search for timezones
- ✅ Memoized components
- ✅ Optimized re-renders
- ✅ LocalStorage caching of preferences

## Browser Support

- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- Mobile browsers (iOS Safari, Android Chrome)

## Troubleshooting

### Clock Not Updating
- Check browser console for errors
- Ensure JavaScript is enabled
- Try refreshing the page
- Clear browser cache

### Timezone Not Found
- Check exact timezone name
- Try searching by city name
- Verify timezone in IANA database
- Use timezone code format

### Settings Not Persisting
- Check browser LocalStorage is enabled
- Clear browser cache and cookies
- Try incognito/private mode
- Check browser privacy settings

## API References

### date-fns
- `utcToZonedTime()` - Convert UTC to timezone
- `formatInTimeZone()` - Format time in timezone
- `getTimezoneOffset()` - Get UTC offset

### Day.js
- `dayjs().tz()` - Get timezone support
- `dayjs().format()` - Format dates/times

### Browser APIs
- `Date.now()` - Current timestamp
- `Intl.DateTimeFormat()` - Localization
- `navigator.language` - User language

## Future Enhancements

- ⏰ Alarm functionality
- 📍 Geolocation-based timezone detection
- 🌍 World map with timezones
- 📋 Meeting time finder
- 🔔 Timezone-based notifications
- 📱 Progressive Web App (PWA)
- 🎨 Custom themes
- 📊 Timezone statistics
- 🌐 Shared clock links
- ♿ Advanced accessibility features

## Resources

- [IANA Timezone Database](https://www.iana.org/time-zones)
- [MDN Date/Time Documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date)
- [date-fns Documentation](https://date-fns.org/)
- [Tailwind CSS Docs](https://tailwindcss.com/docs)
- [Next.js Documentation](https://nextjs.org/docs)

## License

MIT - Feel free to use and modify this project

## Support

For issues or questions:
1. Check troubleshooting section
2. Review browser console for errors
3. Verify timezone data in lib/timezones.ts
4. Create an issue on GitHub
