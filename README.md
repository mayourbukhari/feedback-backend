# Feedback App Backend

A Node.js backend API for the feedback system built with Express and MongoDB.

## Features

- User authentication with JWT tokens
- Password hashing with bcrypt
- Feedback CRUD operations
- MongoDB database integration
- CORS enabled for frontend communication
- Environment variable configuration

## Technologies Used

- Node.js
- Express.js 5.1.0
- MongoDB with Mongoose 8.16.1
- JWT for authentication
- bcrypt for password hashing
- dotenv for environment variables
- CORS for cross-origin requests

## Getting Started

1. Install dependencies:
```bash
npm install
```

2. Create a `.env` file in the root directory with the following variables:
```
PORT=5000
MONGODB_URI=mongodb://localhost:27017/feedback-app
JWT_SECRET=your-jwt-secret-key
```

3. Start the development server:
```bash
npm start
```

## API Endpoints

### Authentication
- `POST /api/auth/register` - Register a new user
- `POST /api/auth/login` - Login user

### Feedback
- `GET /api/feedback` - Get all feedback (admin only)
- `POST /api/feedback` - Create new feedback
- `PUT /api/feedback/:id` - Update feedback
- `DELETE /api/feedback/:id` - Delete feedback

## Database Schema

### User
- email: String (unique)
- password: String (hashed)
- role: String (user/admin)

### Feedback
- title: String
- description: String
- user: ObjectId (ref to User)
- status: String (pending/approved/rejected)
- createdAt: Date
- updatedAt: Date

## Environment Variables

- `PORT` - Server port (default: 5000)
- `MONGODB_URI` - MongoDB connection string
- `JWT_SECRET` - Secret key for JWT tokens

## License

This project is licensed under the MIT License.
