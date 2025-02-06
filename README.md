# Quiz Game App (MERN Stack)

## Overview
The **Quiz Game App** is a full-stack web application built using the **MERN stack (MongoDB, Express.js, React.js, Node.js)**. It allows **students/users** to log in and attempt quizzes, while **staff/admins** can manage quizzes, including adding, updating, and categorizing questions.

## Features
### Admin (Staff) Panel
- Login authentication for admin users.
- Create, update, and delete quiz categories (e.g., "Quiz on OS", "Quiz on DBMS").
- Add, edit, and delete quiz questions.
- View student performance and scores.

### Student (User) Panel
- Login authentication for students/users.
- View and select quizzes from different categories.
- Answer quiz questions and submit responses.
- Receive immediate final score.

## Tech Stack
### Frontend
- React.js (Vite for fast development)
- Tailwind CSS (for styling)
- React Router (for navigation)
- Axios (for API requests)

### Backend
- Node.js
- Express.js
- MongoDB (Database for quizzes, users, and scores)
- Mongoose (ODM for MongoDB)
- JWT (JSON Web Token for authentication)
- bcrypt.js (for password hashing)

## Installation Guide

### Prerequisites
Ensure you have the following installed:
- Node.js (LTS version)
- MongoDB (local or cloud-based using MongoDB Atlas)

### Clone the Repository
```sh
git clone https://github.com/yourusername/quiz-game-app.git
cd quiz-game-app
```

### Backend Setup
```sh
cd backend
npm install
```

Create a `.env` file inside the backend folder and add the following variables:
```env
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_secret_key
```

Run the backend server:
```sh
npm run dev
```

### Frontend Setup
```sh
cd frontend
npm install
```

Run the frontend application:
```sh
npm run dev
```

## API Routes

### Auth Routes
| Method | Endpoint      | Description |
|--------|-------------|-------------|
| POST   | /api/auth/register | Register a new user (student/admin) |
| POST   | /api/auth/login    | Login user (returns JWT token) |

### Quiz Management (Admin Only)
| Method | Endpoint | Description |
|--------|---------|-------------|
| POST   | /api/quizzes | Create a new quiz |
| PUT    | /api/quizzes/:id | Update a quiz |
| DELETE | /api/quizzes/:id | Delete a quiz |
| GET    | /api/quizzes | Fetch all quizzes |

### Quiz Participation (Users)
| Method | Endpoint | Description |
|--------|---------|-------------|
| GET    | /api/quizzes/:id | Get quiz questions by ID |
| POST   | /api/quizzes/:id/submit | Submit quiz answers and get a score |

