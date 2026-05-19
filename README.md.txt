# Task Management API with MongoDB

## 📌 Project Overview

The Task Management API is a secure RESTful backend application built using Node.js, Express.js, MongoDB Atlas, and Mongoose. The application allows users to register, authenticate, and manage personal tasks with full CRUD functionality, validation, pagination, filtering, and user-based access control.

This project demonstrates backend development best practices including authentication, database integration, API development, schema validation, and clean code architecture.

---

# 🚀 Technologies Used

- Node.js
- Express.js
- MongoDB Atlas
- Mongoose ODM
- JWT Authentication
- bcryptjs
- dotenv
- Nodemon

---

# 📁 Project Structure

```bash
task-management-api/
│
├── server.js
├── package.json
├── .env.example
│
└── src/
    ├── config/
    │   └── database.js
    │
    ├── controllers/
    │   ├── taskController.js
    │   └── userController.js
    │
    ├── middleware/
    │   └── auth.js
    │
    ├── models/
    │   ├── Task.js
    │   └── User.js
    │
    └── routes/
        ├── taskRoutes.js
        └── userRoutes.js
```

---

# ⚙️ Installation & Setup

## 1️⃣ Clone Repository

```bash
git clone https://github.com/your-username/task-management-api.git
```

---

## 2️⃣ Navigate to Project Folder

```bash
cd task-management-api
```

---

## 3️⃣ Install Dependencies

```bash
npm install
```

---

## 4️⃣ Configure Environment Variables

Create a `.env` file in the project root directory.

Example:

```env
PORT=5000

MONGODB_URI=your_mongodb_atlas_connection_string

JWT_SECRET_KEY=your_secret_jwt_key

NODE_ENV=development
```

---

## 5️⃣ Start Development Server

```bash
npm run dev
```

---

# 🌐 MongoDB Atlas Setup

## Step 1: Create MongoDB Atlas Account

- Visit MongoDB Atlas
- Create a free account
- Create a free cluster

---

## Step 2: Create Database User

- Navigate to Database Access
- Create username and password

---

## Step 3: Whitelist IP Address

- Navigate to Network Access
- Add current IP address
- Allow access from anywhere (`0.0.0.0/0`) for testing

---

## Step 4: Get Connection String

- Click "Connect"
- Select "Connect your application"
- Copy MongoDB URI

Example:

```bash
mongodb+srv://username:password@cluster.mongodb.net/task_management_db
```

---

# 🔐 Authentication System

The application uses JWT (JSON Web Token) authentication.

## Authentication Flow

1. User registers or logs in
2. Server generates JWT token
3. Token is returned to client
4. Client sends token in Authorization header
5. Middleware verifies token
6. Protected routes become accessible

---

# 🗄️ Database Schema Design

## 👤 User Schema

| Field | Type | Validation |
|---|---|---|
| name | String | Required |
| email | String | Required, Unique |
| password | String | Required, Hashed |

---

## ✅ Task Schema

| Field | Type | Validation |
|---|---|---|
| title | String | Required |
| description | String | Optional |
| completed | Boolean | Default false |
| priority | String | Enum |
| category | String | Enum |
| dueDate | Date | Optional |
| user | ObjectId | Reference to User |

---

# 🔗 Database Relationship

- One User can have multiple Tasks
- Each Task belongs to one User

Relationship:

```bash
User 1 ---- * Tasks
```

---

# 📌 API Endpoints

# 👤 Authentication Routes

## Register User

```http
POST /api/auth/register
```

### Request Body

```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "password123"
}
```

---

## Login User

```http
POST /api/auth/login
```

### Request Body

```json
{
  "email": "john@example.com",
  "password": "password123"
}
```

---

# ✅ Task Routes (Protected)

## Create Task

```http
POST /api/tasks
```

---

## Get All Tasks

```http
GET /api/tasks
```

### Query Parameters

| Parameter | Description |
|---|---|
| page | Pagination page |
| limit | Number of tasks |
| completed | true / false |
| priority | low / medium / high |
| category | task category |

Example:

```http
GET /api/tasks?page=1&limit=5&priority=high
```

---

## Get Single Task

```http
GET /api/tasks/:id
```

---

## Update Task

```http
PUT /api/tasks/:id
```

---

## Delete Task

```http
DELETE /api/tasks/:id
```

---

# 🧪 Testing

API endpoints were tested using:

- Postman
- MongoDB Compass

Testing includes:

- User registration
- Login authentication
- Protected route validation
- CRUD operations
- Pagination and filtering
- Error handling

---

# 📊 Features Implemented

✅ User Authentication using JWT  
✅ Password Hashing using bcryptjs  
✅ MongoDB Atlas Integration  
✅ Mongoose Schema Validation  
✅ CRUD Operations  
✅ Pagination  
✅ Filtering & Sorting  
✅ Protected Routes  
✅ Database Relationships  
✅ Error Handling  
✅ Clean Folder Structure  

---

# 🛡️ Security Features

- Password hashing
- JWT token authentication
- Protected routes
- Environment variable configuration
- Schema validation

---

# 📈 Performance Optimization

- MongoDB indexes added
- Efficient filtering queries
- Pagination implemented
- Optimized database lookups

---

# 💡 Clean Coding Practices Followed

- Meaningful variable names
- Modular folder structure
- Reusable middleware
- Proper error handling
- Separation of concerns
- Consistent formatting
- Environment-based configuration

---

# 📷 Screenshots Required for Submission

Include screenshots for:

- MongoDB Atlas connection
- User registration API
- User login API
- Task CRUD operations
- MongoDB Compass collections
- Pagination and filtering output

---

# 📚 Future Improvements

- Role-based authorization
- Email verification
- Password reset functionality
- Swagger API documentation
- Unit testing
- Docker deployment

---

# 👨‍💻 Author

Manjula Kalluri

---

# 📄 License

This project is created for educational and learning purposes.