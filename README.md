# Sports Platform

A full-stack web application where users can browse sports matches, filter by sport/league, search by team names, and mark their favorite games. Built with modern technologies and a professional UI/UX design.

## Live Demo

- **Frontend**: https://sports-hub-frontend-beryl.vercel.app/login
- **Backend API**: https://sports-hub-backend.vercel.app


## Features

### Core Features ✅

#### User Authentication
- ✅ Register with name, email, and password
- ✅ Login with email and password
- ✅ Passwords securely hashed using bcryptjs
- ✅ JWT-based authentication with 7-day token expiry
- ✅ Protected routes - only authenticated users can access games

#### Games/Matches Listing
- ✅ Display sports matches with complete details
- ✅ Real-time favorite status for each game
- ✅ 21 pre-seeded matches across 5 sports
- ✅ Beautiful card-based UI with sport-specific colors

#### Filter Functionality
- ✅ Filter by Sport (Cricket, Football, Tennis, Basketball, Rugby)
- ✅ Filter by League (IPL, EPL, La Liga, ATP Tour, NBA, Six Nations, etc.)
- ✅ Active filters display with visual chips
- ✅ Dropdown-based filtering UI

#### Favorites Management
- ✅ Mark/unmark games as favorite with star icon
- ✅ Favorites saved in backend database
- ✅ Dedicated Favorites page
- ✅ Real-time UI updates

### Bonus Features ✅

- ✅ **Search** - Search games by team names (real-time)
- ✅ **Protected Routes** - React Router with authentication guards
- ✅ **Fully Responsive Design** - Works on mobile, tablet, and desktop
- ✅ **Hamburger Menu** - Mobile-friendly navigation
- ✅ **Loading States** - Smooth loading animations
- ✅ **Empty States** - User-friendly messages with icons
- ✅ **Error Handling** - Clear error messages with 4-second visibility
- ✅ **Professional UI** - Modern emerald/teal color scheme
- ✅ **Gradient Backgrounds** - Beautiful visual design
- ✅ **Smooth Animations** - Hover effects and transitions

---

## Tech Stack

### Backend
- **Runtime**: Node.js (ES6 Modules)
- **Framework**: Express.js
- **Database**: MongoDB with Mongoose ODM
- **Authentication**: JWT (jsonwebtoken)
- **Password Hashing**: bcryptjs (10 rounds)
- **CORS**: Enabled for cross-origin requests

### Frontend
- **Framework**: React 18
- **Build Tool**: Vite
- **Routing**: React Router DOM v6
- **HTTP Client**: Axios (with interceptors)
- **Styling**: Tailwind CSS v4 (latest)
- **State Management**: React Context API

### Development Tools
- **Backend**: Nodemon for hot reload
- **Frontend**: Vite dev server with HMR
- **Version Control**: Git

---

## Project Structure

```
sports-platform/
├── backend/
│   ├── src/
│   │   ├── config/
│   │   │   └── database.js          # MongoDB connection
│   │   ├── middleware/
│   │   │   └── auth.js              # JWT authentication middleware
│   │   ├── models/
│   │   │   └── index.js             # Mongoose schemas (User, Game, Favorite)
│   │   ├── routes/
│   │   │   ├── auth.js              # Register & Login routes
│   │   │   ├── games.js             # Games CRUD routes
│   │   │   └── favorites.js         # Favorites CRUD routes
│   │   ├── utils/
│   │   │   └── seed.js              # Database seeding script
│   │   └── server.js                # Express app entry point
│   ├── .env                         # Environment variables (not in git)
│   ├── .env.example                 # Example environment file
│   ├── .gitignore
│   └── package.json
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   │   ├── Auth/
│   │   │   │   ├── Login.jsx        # Login page with error handling
│   │   │   │   └── Register.jsx     # Registration page
│   │   │   ├── Games/
│   │   │   │   ├── GamesList.jsx    # Main games listing page
│   │   │   │   ├── GameCard.jsx     # Individual game card
│   │   │   │   ├── FilterBar.jsx    # Filter & search component
│   │   │   │   └── Favorites.jsx    # Favorites page
│   │   │   └── Layout/
│   │   │       ├── Navbar.jsx       # Responsive navbar with hamburger
│   │   │       └── ProtectedRoute.jsx # Route protection
│   │   ├── context/
│   │   │   └── AuthContext.jsx      # Global auth state management
│   │   ├── services/
│   │   │   └── api.js               # Axios instance & API calls
│   │   ├── App.jsx                  # Main app component
│   │   ├── main.jsx                 # Entry point
│   │   └── index.css                # Tailwind imports
│   ├── .env                         # Environment variables (not in git)
│   ├── .env.example                 # Example environment file
│   ├── .gitignore
│   ├── index.html
│   ├── package.json
│   ├── vite.config.js               # Vite configuration
│   └── tailwind.config.js           # Tailwind configuration
│
├── .gitignore
└── README.md
```

---

## Installation & Setup

### Prerequisites

- **Node.js** (v18 or higher)
- **MongoDB** (Local installation OR MongoDB Atlas account)
- **npm** or **yarn**

### Step 1: Clone the Repository

```bash
git clone https://github.com/yourusername/sports-platform.git
cd sports-platform
```

### Step 2: Backend Setup

```bash
# Navigate to backend directory
cd backend

# Install dependencies
npm install

# Create environment file
cp .env.example .env
```

**Edit `.env` file:**

For **Local MongoDB**:
```env
PORT=5000
MONGODB_URI=
JWT_SECRET=your-super-secret-jwt-key-change-in-production
NODE_ENV=development
```

For **MongoDB Atlas**:
```env
PORT=5000
MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/sports_platform
JWT_SECRET=your-super-secret-jwt-key-change-in-production
NODE_ENV=development
```

**Seed the database:**
```bash
npm run seed
```

You should see:
```
✅ MongoDB Connected for seeding...
   Seeding database...
✅ Successfully seeded 21 matches!
✅ Database connection closed
```

**Start the backend server:**
```bash
npm run dev
```

Backend runs on: **http://localhost:5000**

### Step 3: Frontend Setup

Open a **new terminal** and:

```bash
# Navigate to frontend directory
cd frontend

# Install dependencies
npm install

# Install Tailwind CSS v4
npm install tailwindcss @tailwindcss/vite

# Create environment file
cp .env.example .env
```

**Edit `.env` file:**
```env
VITE_API_URL=http://localhost:5000
```

**Start the frontend:**
```bash
npm run dev
```

Frontend runs on: **http://localhost:5173**

---

## API Endpoints

### Authentication Endpoints

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| POST | `/api/auth/register` | Register a new user | No |
| POST | `/api/auth/login` | Login user | No |

### Games Endpoints

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| GET | `/api/games` | Get all games | Yes |
| GET | `/api/games?sport=Cricket` | Filter games by sport | Yes |
| GET | `/api/games?league=IPL` | Filter games by league | Yes |
| GET | `/api/games?search=Mumbai` | Search games by team name | Yes |
| GET | `/api/games/sports` | Get all unique sports | Yes |
| GET | `/api/games/leagues` | Get all unique leagues | Yes |

### Favorites Endpoints

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| GET | `/api/favorites` | Get user's favorite games | Yes |
| POST | `/api/favorites/:gameId` | Add game to favorites | Yes |
| DELETE | `/api/favorites/:gameId` | Remove game from favorites | Yes |

### Example API Requests

**Register User:**
```bash
POST /api/auth/register
Content-Type: application/json

{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "password123"
}

Response (201):
{
  "message": "User registered successfully",
  "user": {
    "id": "507f1f77bcf86cd799439011",
    "name": "John Doe",
    "email": "john@example.com"
  },
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
}
```

**Login:**
```bash
POST /api/auth/login
Content-Type: application/json

{
  "email": "john@example.com",
  "password": "password123"
}

Response (200):
{
  "message": "Login successful",
  "user": {
    "id": "507f1f77bcf86cd799439011",
    "name": "John Doe",
    "email": "john@example.com"
  },
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
}
```

**Get Games:**
```bash
GET /api/games
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...

Response (200):
{
  "games": [
    {
      "id": "507f1f77bcf86cd799439011",
      "sport": "Cricket",
      "league": "IPL",
      "team_a": "Mumbai Indians",
      "team_b": "Chennai Super Kings",
      "start_time": "2026-01-05T19:30:00.000Z",
      "is_favorite": true
    }
  ],
  "count": 1
}
```

---

## Environment Variables

### Backend `.env`

```env
# Server Port
PORT=5000

# MongoDB Connection String
# Local: mongodb://localhost:27017/sports_platform
# Atlas: mongodb+srv://username:password@cluster.mongodb.net/sports_platform
MONGODB_URI=mongodb://localhost:27017/sports_platform

# JWT Secret Key (change in production!)
JWT_SECRET=your-super-secret-jwt-key-change-in-production

# Environment
NODE_ENV=development
```

### Frontend `.env`

```env
# Backend API URL
VITE_API_URL=http://localhost:5000
```

---

## Database Schema

### User Model (Mongoose)

```javascript
{
  name: String (required, trimmed),
  email: String (required, unique, lowercase, trimmed),
  password: String (required, hashed),
  createdAt: Date (auto),
  updatedAt: Date (auto)
}
```

### Game Model (Mongoose)

```javascript
{
  sport: String (required, trimmed),
  league: String (required, trimmed),
  team_a: String (required, trimmed),
  team_b: String (required, trimmed),
  start_time: Date (required),
  createdAt: Date (auto),
  updatedAt: Date (auto)
}

Indexes: sport, league, start_time
```

### Favorite Model (Mongoose)

```javascript
{
  user: ObjectId (ref: User, required),
  game: ObjectId (ref: Game, required),
  createdAt: Date (auto),
  updatedAt: Date (auto)
}

Indexes: user, unique(user + game)
```

---

## Testing the Application

### Manual Testing Steps

1. **Open browser** and navigate to `http://localhost:5173`

2. **Register a new account:**
   - Click "Register here"
   - Enter name, email, and password (min 6 characters)
   - Click "Register"

3. **Login:**
   - Enter email and password
   - Click "Login"
   - You'll be redirected to games page

4. **Browse Games:**
   - See 21 seeded matches
   - Scroll through different sports

5. **Use Filters:**
   - Select a sport from dropdown (e.g., Cricket)
   - Select a league (e.g., IPL)
   - See filtered results

6. **Search:**
   - Type a team name (e.g., "Mumbai")
   - See real-time search results

7. **Add Favorites:**
   - Click the star (☆) icon on any game card
   - Star becomes filled (⭐)

8. **View Favorites:**
   - Click "Favorites" in navigation
   - See all your favorited games

9. **Remove Favorites:**
   - Click the filled star (⭐) on any game
   - Game is removed from favorites

10. **Logout:**
    - Click "Logout" button
    - Redirected to login page

### Mobile Testing

1. Open browser DevTools (F12)
2. Toggle device toolbar (Ctrl+Shift+M)
3. Select mobile device (iPhone 12, etc.)
4. Test hamburger menu and all features

---

## Contributing

This is an assessment project and is not accepting contributions.

---

## License

This project is created for educational and assessment purposes.

---

## Developer

**Kartik Rathod**  
Email: rathodkartik293@gmail.com
GitHub:https://github.com/kartikrathod23

---


**Built with ❤️ using MERN Stack**  
**MongoDB • Express • React • Node.js**

---

**Submission Date**:1 January 2026  
**Assessment Duration**: 4 Days (Jan 1-4, 2026)  
**Project Status**: ✅ Complete
