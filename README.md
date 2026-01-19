# Uber Clone

A full-stack ride-sharing application built with modern web technologies. This project demonstrates a complete implementation of a ride-sharing platform with user authentication, ride booking, and driver management.

## 🚀 Features

- **User Authentication**: Secure login and registration for riders and drivers
- **Ride Booking**: Intuitive interface for booking rides with real-time status updates
- **Driver Management**: Driver registration, dashboard, and ride acceptance
- **Real-time Updates**: Live ride status tracking and confirmation
- **Map Integration**: Interactive maps using Leaflet for location selection and route planning
- **Responsive Design**: Modern UI built with React and Tailwind CSS
- **Secure Backend**: JWT-based authentication and encrypted passwords with bcrypt

## 🛠️ Tech Stack

### Frontend
- **React 19** - UI library with latest features
- **Vite 7** - Lightning-fast build tool and dev server
- **React Router 7** - Client-side routing
- **Tailwind CSS 4** - Utility-first CSS framework
- **Leaflet** - Open-source mapping library
- **Axios** - HTTP client for API requests
- **React Icons** - Icon library

### Backend
- **Node.js/Express 5** - Server runtime and web framework
- **MSSQL** - Microsoft SQL Server database
- **JWT (jsonwebtoken)** - Authentication tokens
- **bcrypt** - Password hashing
- **CORS** - Cross-origin request handling
- **dotenv** - Environment variable management

## 📁 Project Structure

```
Uber/
├── backend/                    # Express.js server
│   ├── config/
│   │   └── dbConfig.js        # Database configuration
│   ├── controllers/           # Business logic
│   │   ├── userController.js
│   │   ├── driverController.js
│   │   └── rideController.js
│   ├── routes/                # API routes
│   │   ├── userRoutes.js
│   │   ├── driverRoutes.js
│   │   └── rideRoutes.js
│   ├── server.js              # Server entry point
│   └── package.json
│
└── frontend/                  # React + Vite application
    ├── src/
    │   ├── components/        # Reusable components
    │   │   └── Navbar.jsx
    │   ├── pages/             # Page components
    │   │   ├── Home.jsx
    │   │   ├── UserLogin.jsx
    │   │   ├── UserRegister.jsx
    │   │   ├── UserDashboard.jsx
    │   │   ├── BookRide.jsx
    │   │   ├── RideConfirm.jsx
    │   │   ├── RideStatus.jsx
    │   │   ├── DriverLogin.jsx
    │   │   ├── DriverRegister.jsx
    │   │   └── DriverDashboard.jsx
    │   ├── assets/            # Static assets
    │   ├── App.jsx            # Root component
    │   └── main.jsx           # Entry point
    ├── vite.config.js         # Vite configuration
    ├── package.json
    └── index.html
```

## 🔧 Installation

### Prerequisites
- Node.js (v16 or higher)
- npm or yarn package manager
- MSSQL Server instance running

### Backend Setup

1. Navigate to the backend directory:
   ```bash
   cd backend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Create a `.env` file in the backend directory with your database configuration:
   ```env
   DB_SERVER=your_server_name
   DB_USER=your_username
   DB_PASSWORD=your_password
   DB_DATABASE=your_database_name
   DB_PORT=1433
   JWT_SECRET=your_jwt_secret_key
   ```

4. Start the server:
   ```bash
   npm start
   ```
   or with nodemon for development:
   ```bash
   npx nodemon server.js
   ```

The backend server will run on `http://localhost:5000`

### Frontend Setup

1. Navigate to the frontend directory:
   ```bash
   cd frontend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start the development server:
   ```bash
   npm run dev
   ```

4. Build for production:
   ```bash
   npm run build
   ```

The frontend will be available at `http://localhost:5173` (default Vite port)

## 📚 API Endpoints

### Users API (`/api/users`)
- `POST /register` - Register a new user
- `POST /login` - User login
- `GET /profile` - Get user profile
- `PUT /profile` - Update user profile

### Drivers API (`/api/drivers`)
- `POST /register` - Register a new driver
- `POST /login` - Driver login
- `GET /dashboard` - Get driver dashboard
- `PUT /accept-ride` - Accept a ride request

### Rides API (`/api/rides`)
- `POST /book` - Book a new ride
- `GET /status/:rideId` - Get ride status
- `GET /history` - Get ride history
- `PUT /complete` - Mark ride as complete

## 🔐 Authentication

The application uses JWT (JSON Web Tokens) for authentication:

1. Users/drivers register or login to receive a token
2. The token is stored in local storage on the frontend
3. All protected API requests include the token in the Authorization header
4. Passwords are encrypted using bcrypt before storage

## 🗄️ Database

The application uses MSSQL Server. Ensure your database has the following tables:
- Users
- Drivers
- Rides

Refer to your database setup scripts for the complete schema.

## 🚦 Getting Started Quickly

```bash
# Clone or extract the project
cd Uber

# Backend
cd backend
npm install
# Configure .env file
npm start

# Frontend (in a new terminal)
cd frontend
npm install
npm run dev
```

Visit `http://localhost:5173` in your browser to see the application.

## 📝 Development

### Frontend Commands
- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run preview` - Preview production build
- `npm run lint` - Run ESLint

### Backend Commands
- `npm start` - Start the server
- `npx nodemon server.js` - Start with auto-reload

## 🐛 Troubleshooting

### Database Connection Issues
- Verify MSSQL Server is running
- Check database credentials in `.env`
- Ensure firewall allows connections to the database port

### CORS Errors
- Backend CORS is configured to accept requests
- Check frontend URL matches backend CORS configuration

### Port Already in Use
- Change the port in `server.js` (backend) or `vite.config.js` (frontend)

## 🤝 Contributing

Contributions are welcome! Please feel free to submit pull requests or open issues for bugs and feature requests.

## 📄 License

ISC License

## 👨‍💻 Author

Your Name / Organization

---

**Note**: This is a development version. For production deployment, ensure proper security configurations, environment variables, and database backups.
