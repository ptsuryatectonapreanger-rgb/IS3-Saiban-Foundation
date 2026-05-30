# Setup Guide - IS3 Saiban Foundation

## Prerequisites
- Node.js v16+ & npm v8+
- MongoDB (local atau MongoDB Atlas)
- Git

## Installation

### 1. Clone Repository
```bash
git clone https://github.com/ptsuryatectonapreanger-rgb/IS3-Saiban-Foundation.git
cd IS3-Saiban-Foundation
```

### 2. Setup Backend

```bash
cd backend
npm install
```

Create `.env` file:
```bash
cp .env.example .env
```

Edit `.env` dengan konfigurasi Anda:
```env
PORT=5000
MONGODB_URI=mongodb://localhost:27017/shopee
JWT_SECRET=your_secret_key
STRIPE_PUBLIC_KEY=your_key
STRIPE_SECRET_KEY=your_key
```

Run migrations & seed data (opsional):
```bash
npm run seed
```

Start backend:
```bash
npm run dev
```

Backend akan berjalan di `http://localhost:5000`

### 3. Setup Frontend

```bash
cd frontend
npm install
```

Create `.env.local`:
```bash
cp .env.example .env.local
```

Start frontend:
```bash
npm run dev
```

Frontend akan berjalan di `http://localhost:3000`

### 4. Verifikasi Setup

Buka browser:
- Frontend: http://localhost:3000
- Backend API: http://localhost:5000/api

## Database Setup

### Menggunakan MongoDB Local
```bash
# macOS dengan Homebrew
brew services start mongodb-community

# Windows
mongod

# Linux
sudo systemctl start mongod
```

### Menggunakan MongoDB Atlas (Cloud)
1. Daftar di https://www.mongodb.com/cloud/atlas
2. Buat cluster gratis
3. Copy connection string
4. Update `MONGODB_URI` di `.env`

## Development Workflow

### Running Everything
```bash
npm run dev  # Dari root directory
```

### Running Separately
```bash
# Terminal 1 - Backend
cd backend && npm run dev

# Terminal 2 - Frontend
cd frontend && npm run dev
```

### Code Style
```bash
npm run lint  # Check linting
npm run format  # Format code (opsional)
```

## Testing

```bash
# Backend tests
cd backend && npm test

# Frontend tests
cd frontend && npm test
```

## Building for Production

```bash
# Build semua
npm run build

# Build terpisah
cd backend && npm run build
cd frontend && npm run build
```

## Troubleshooting

### Port Already in Use
```bash
# Change PORT in .env
PORT=5001

# atau kill process
lsof -ti:5000 | xargs kill -9  # macOS/Linux
netstat -ano | findstr :5000   # Windows
```

### MongoDB Connection Error
- Pastikan MongoDB service berjalan
- Check connection string di `.env`
- Verify firewall settings

### Module Not Found
```bash
# Delete node_modules dan reinstall
rm -rf node_modules package-lock.json
npm install
```

## Environment Variables

### Backend (.env)
- `PORT` - Server port
- `NODE_ENV` - Development/production
- `MONGODB_URI` - Database connection string
- `JWT_SECRET` - JWT signing key
- `STRIPE_*` - Stripe API keys

### Frontend (.env.local)
- `NEXT_PUBLIC_API_URL` - Backend API URL

## Security Notes
- Jangan commit `.env` files
- Use `.env.example` untuk template
- Rotate secrets regularly
- Enable HTTPS in production

## Resources
- [Next.js Documentation](https://nextjs.org/docs)
- [Express.js Documentation](https://expressjs.com/)
- [MongoDB Documentation](https://docs.mongodb.com/)
- [Tailwind CSS Documentation](https://tailwindcss.com/docs)

## Support
Untuk pertanyaan atau issues:
1. Buat GitHub Issue
2. Describe problem dengan detail
3. Include error messages & logs
