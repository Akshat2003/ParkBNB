# ParkBNB - Smart Parking Marketplace Platform

A comprehensive parking marketplace platform that connects vehicle owners seeking parking with property owners offering parking spaces. Built with modern technologies for scalability and user experience.

## 🚀 Project Overview

ParkBNB is designed to simplify parking discovery, enable seamless bookings, and empower space owners to monetize their unused parking spaces. The platform supports three user roles: **Users** (drivers), **Owners** (space providers), and **Admins** (platform managers).

## 📁 Project Structure

```
parkingbnb/
├── frontend/              # React + Vite + Tailwind CSS
│   ├── src/
│   │   ├── components/    # Reusable UI components
│   │   ├── pages/         # Page components (Home, Login, Dashboards, etc.)
│   │   ├── services/      # API service layer
│   │   ├── context/       # React Context (Authentication)
│   │   ├── layouts/       # Layout components
│   │   └── utils/         # Utility functions
│   └── package.json
│
├── backend/               # Node.js + Express + MongoDB
│   ├── src/
│   │   ├── config/        # Database and app configuration
│   │   ├── models/        # Mongoose data models (20 models)
│   │   ├── routes/        # API route definitions
│   │   ├── controllers/   # Route controller logic
│   │   ├── middleware/    # Custom middleware (auth, validation)
│   │   └── utils/         # Utility functions
│   └── package.json
│
├── About.txt              # Detailed project description
└── DataModels.txt         # Complete database schema (ERD format)
```

## 🎯 Key Features

### For Users (Drivers)
- 🔍 **Smart Search** - Map-based parking space discovery with filters
- 📅 **Flexible Booking** - Hourly, daily, weekly, or monthly reservations
- 🚗 **Vehicle Management** - Save and manage multiple vehicles
- 💳 **Multiple Payment Methods** - Credit/debit cards, UPI, wallets
- ⭐ **Reviews & Ratings** - Rate parking experiences
- 💬 **In-App Messaging** - Communicate with space owners

### For Owners
- 🏢 **Property Management** - List properties and parking spaces
- 💰 **Dynamic Pricing** - Set flexible pricing models
- 📊 **Analytics Dashboard** - Track earnings, bookings, and occupancy
- 📱 **Booking Notifications** - Real-time booking alerts
- 🎯 **Owner Types** - Individual, Residential, Commercial, Industrial, Land-based
- ✅ **KYC Verification** - Build trust with verified profiles

### For Admins
- 👥 **User Management** - Manage users and owners
- 🏘️ **Property Approval** - Verify and approve listings
- 💵 **Payment Oversight** - Monitor transactions and refunds
- 🎟️ **Support Tickets** - Handle customer support
- ⚙️ **Platform Settings** - Configure commissions and settings
- 📈 **Analytics** - Platform-wide insights and reports

## 🛠️ Technology Stack

### Frontend
- **React 18** - Modern UI library
- **Vite** - Fast build tool and dev server
- **Tailwind CSS** - Utility-first styling
- **React Router DOM** - Client-side routing
- **Axios** - HTTP client for API calls
- **Context API** - State management

### Backend
- **Node.js** - JavaScript runtime
- **Express.js** - Web application framework
- **MongoDB** - NoSQL database
- **Mongoose** - Object Data Modeling (ODM)
- **JWT** - Secure authentication
- **bcryptjs** - Password hashing

## 📦 Installation & Setup

### Prerequisites
- Node.js v16 or higher
- MongoDB (local installation or MongoDB Atlas)
- npm or yarn package manager

### Backend Setup

1. Navigate to backend directory:
```bash
cd backend
```

2. Install dependencies:
```bash
npm install
```

3. Create environment file:
```bash
cp .env.example .env
```

4. Configure `.env` file:
```env
PORT=5000
NODE_ENV=development
MONGODB_URI=mongodb://localhost:27017/parkingbnb
JWT_SECRET=your_secure_jwt_secret_key
JWT_EXPIRE=7d
FRONTEND_URL=http://localhost:5173
```

5. Start the development server:
```bash
npm run dev
```

Backend will run on `http://localhost:5000`

### Frontend Setup

1. Navigate to frontend directory:
```bash
cd frontend
```

2. Install dependencies:
```bash
npm install
```

3. Create environment file:
```bash
cp .env.example .env
```

4. Configure `.env` file:
```env
VITE_API_URL=http://localhost:5000/api
```

5. Start the development server:
```bash
npm run dev
```

Frontend will run on `http://localhost:5173`

## 🗄️ Database Models

The platform includes 20 comprehensive data models:

### User Management
- **User** - User accounts and authentication
- **UserVehicle** - User-owned vehicles
- **UserPaymentMethod** - Saved payment methods

### Property & Parking
- **Owner** - Property owner profiles
- **Property** - Property locations
- **ParkingSpace** - Individual parking spots
- **SpaceAvailability** - Weekly availability schedules

### Bookings & Payments
- **Booking** - Reservation records
- **Payment** - Payment transactions
- **Refund** - Refund processing

### Communication
- **Review** - User reviews and ratings
- **Conversation** - User-owner conversations
- **Message** - Individual messages
- **Notification** - System notifications

### Promotions & Support
- **PromoCode** - Promotional discount codes
- **PromoCodeUsage** - Usage tracking
- **SupportTicket** - Customer support tickets
- **TicketMessage** - Support conversation messages

### Administration
- **Admin** - Admin user management
- **PlatformSettings** - System configuration

## 🌐 API Endpoints

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - User login
- `GET /api/auth/me` - Get current user (protected)

More endpoints will be added as features are developed.

## 🎨 Frontend Pages

- **/** - Landing page with hero and features
- **/login** - User authentication
- **/register** - User registration with role selection
- **/user/dashboard** - User dashboard (search, bookings, vehicles, profile)
- **/owner/dashboard** - Owner dashboard (properties, spaces, bookings, earnings)
- **/admin/dashboard** - Admin panel (users, owners, properties, payments, settings)

## 🔐 Authentication Flow

1. User registers with email, phone, password, and user type
2. Password is hashed using bcrypt before storage
3. Upon login, JWT token is generated and returned
4. Token is stored in localStorage and sent with API requests
5. Protected routes verify token using auth middleware

## 🚧 Development Status

### ✅ Completed
- Full project structure setup
- 20 Mongoose data models
- Frontend with 7 responsive pages
- Authentication system (register, login)
- JWT-based authorization
- React Context for state management
- Tailwind CSS styling
- API service layer

### 🔄 Next Steps
- Implement remaining API endpoints (properties, bookings, payments)
- Add map integration (Google Maps/Mapbox)
- Payment gateway integration (Razorpay/Stripe)
- Real-time notifications (Socket.io)
- Image upload functionality
- Advanced search and filtering
- Analytics dashboards
- Mobile app (React Native)

## 🤝 Contributing

Contributions are welcome! Please follow these steps:
1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Open a pull request

## 📄 License

ISC

## 👥 Support

For questions or support, please create an issue in the repository.

---

**Built with ❤️ for the ParkBNB platform**
