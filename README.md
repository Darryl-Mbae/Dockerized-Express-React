# Docker Server & Client Starter

A simple **Dockerized** setup with **Vite (React Client)** and **Express (Server)**, including **Redis caching**, **Helmet for security**, **Prisma ORM**, and other essential tools for development and production.

## Features

- **Vite + React** - Modern frontend framework with fast HMR support
- **Express.js** - Lightweight and fast backend framework
- **Nodemon** - Automatically restarts the server during development
- **ESLint** - Ensures consistent code formatting and style
- **Dotenv** - Manages environment variables for local and production environments
- **Redis** - Used for caching and session management
- **Prisma ORM** - Modern database toolkit for PostgreSQL, MySQL, or SQLite
- **Helmet.js** - Adds security headers to protect the application
- **Docker Support** - Fully containerized setup with separate **frontend** and **backend** services
- **Modular Structure** - Organized into `middleware`, `routes`, `controllers`, etc.

## Folder Structure

```
project/
├── client/                   # Frontend (Vite + React)
│   ├── src/                  # React source files
│   ├── public/               # Static assets
│   ├── index.html            # Main HTML file
│   ├── package.json          # Frontend dependencies
│   ├── vite.config.js        # Vite configuration
│   └── ...                   # Other frontend files
│
├── server/                   # Backend (Express + Node.js)
│   ├── config/               # Configuration files
│   ├── controllers/          # Business logic for routes
│   ├── middleware/           # Custom middleware
│   ├── routes/               # Route handlers
│   ├── .env.development      # Local environment variables
│   ├── .env.production       # Production environment variables
│   ├── .gitignore            # Git ignored files (e.g., node_modules, .env)
│   ├── app.js                # Main entry point
│   ├── eslint.config.js      # ESLint configuration
│   ├── package.json          # Backend dependencies
│   ├── package-lock.json     # Dependency lock file
│   └── prisma/               # Prisma ORM schema and migrations
│
├── docker-compose.yml        # Docker Compose setup for frontend, backend, and Redis
├── Dockerfile.client         # Docker configuration for frontend
├── Dockerfile.server         # Docker configuration for backend
└── README.md                 # Project documentation
```

## Installation Guide

Follow these steps to set up and run the project on your local machine.

### 1. Clone the Repository
```sh
npx degit Darryl-Mbae/dockerized-express-react .
```


### 2. Install Dependencies in  each folder
 (optional docker will handle that )
 
For the frontend:
```sh
cd client && npm install
```
For the backend:
```sh
cd ../server && npm install
```

### 4. Set Up Environment Variables
Create `.env` files for both `server/` and `client/`.

Example **server/.env**:
```sh
DATABASE_URL=postgresql://user:password@localhost:5432/mydb
REDIS_URL=redis://localhost:6379
```

### 5. Set Up Prisma
Initialize Prisma client:
```sh
npx prisma init
```
Apply migrations to the database:
```sh
npx prisma migrate dev
```

### 6. Run the Project with Docker 
Proof read and  edit dockerfile to your liking

Start everything using Docker Compose:
```sh
sudo docker-compose up 
```


### 7. Access the Application
- **Frontend**: `http://localhost:5173`
- **Backend API**: `http://localhost:5000`
- **Redis**: Runs internally on port `6379`

## Running Without Docker
If you prefer running the app without Docker:

For the **frontend**:
```sh
cd client
npm run dev
```

For the **backend**:
```sh
cd server
npm run dev
```



## Security & Best Practices
- ✅ **Helmet.js** is enabled for additional security headers.
- ✅ **Redis caching** is used to improve performance.
- ✅ **Environment variables** are used for secure configuration.
- ✅ **ESLint** ensures clean and consistent code.
- ✅ **Dockerized setup** ensures easy deployment and scalability.

---

🚀 Enjoy your **Dockerized Express + React** setup! Let me know if you need further improvements! 😃

