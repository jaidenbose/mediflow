# MediFlow - System Architecture

## Overview

MediFlow follows a client-server architecture:

┌─────────────┐ ┌──────────────┐ ┌─────────────┐
│ React │────▶│ Node.js │────▶│ MongoDB │
│ Frontend │◀────│ Backend API │◀────│ Database │
└─────────────┘ └──────────────┘ └─────────────┘


## Components

### 1. Frontend (Client)
- Built with React
- Runs in the user's browser
- Makes API calls to backend
- Displays data to users

### 2. Backend (Server)
- Built with Node.js + Express
- Handles API requests
- Processes business logic
- Talks to database

### 3. Database
- MongoDB (NoSQL database)
- Stores users, hospitals, appointments

## Data Flow Example

1. User opens app → Frontend loads
2. Frontend asks backend for hospitals
3. Backend gets hospitals from database
4. Backend sends data to frontend
5. Frontend displays hospitals to user

## API Design (Planned)

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | /api/auth/register | Create new account |
| POST | /api/auth/login | Login to account |
| GET | /api/hospitals | Get all hospitals |
| GET | /api/hospitals/:id | Get single hospital |
| POST | /api/appointments | Book appointment |
| GET | /api/appointments/my | Get my appointments |

## Folder Structure Explanation

server/
├── config/ # Database connection, environment variables
├── models/ # Database schemas (User, Hospital, Appointment)
├── routes/ # API endpoints
├── controllers/ # Logic for each route
├── middleware/ # Authentication, validation
└── server.js # Entry point

client/
├── public/ # Static files
├── src/
│ ├── components/ # Reusable UI pieces (Button, Card, etc.)
│ ├── pages/ # Full pages (Home, Login, Dashboard)
│ ├── services/ # API calls
│ └── App.js # Main component


## Why This Architecture?

- **Separation of concerns**: Frontend and backend are independent
- **Scalability**: Can add more servers as users grow
- **Maintainability**: Each part has clear responsibility
- **Learnability**: Standard pattern, easy to find help online