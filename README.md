 # 📝 Blog REST API

A simple **Blog REST API** built using **Node.js, Express.js, MongoDB, and Mongoose**.

This project provides complete **CRUD operations** for blog posts through REST APIs.

---

## 📌 Project Information

**Project Name:** Blog REST API  
**Project Type:** REST API / Backend Project  
**Backend:** Node.js + Express.js  
**Database:** MongoDB  
**ODM:** Mongoose  

### 🔗 GitHub Repository
https://github.com/yashmarviya99/node_pr6-blog.git

### 🎥 Project Explanation Video
https://drive.google.com/drive/folders/1TburdB_QcmBOnovONcRAj5gCM2euKWbW

---

## 🚀 Features

- Create a new blog
- Get all blogs
- Get a single blog by ID
- Update a blog
- Delete a blog
- MongoDB database connection using Mongoose
- REST API routing
- Express middleware
- Environment variables using dotenv
- CORS support
- Nodemon for development

---

## 🛠️ Technologies Used

- **Node.js**
- **Express.js**
- **MongoDB**
- **Mongoose**
- **dotenv**
- **CORS**
- **Nodemon**
- **Postman** for API testing

---

## 📁 Project Structure

```text
node_pr6-blog/
│
├── src/
│   ├── controllers/
│   │   └── blogController.js
│   │
│   ├── db/
│   │   └── db.js
│   │
│   ├── models/
│   │   └── blogModel.js
│   │
│   └── routes/
│       └── blogRoute.js
│
├── .env
├── .gitignore
├── package.json
├── package-lock.json
├── server.js
└── README.md
```

---

## 🏗️ Architecture

This project follows the **MVC-style structure**:

```text
Client / Postman
       ↓
Express Server
       ↓
Routes
       ↓
Controllers
       ↓
Mongoose Model
       ↓
MongoDB
       ↓
Response
```

### Folder Responsibilities

**controllers/**  
Contains the main logic for creating, reading, updating, and deleting blogs.

**models/**  
Contains the Mongoose schema and Blog model.

**routes/**  
Defines API endpoints and connects them with controller functions.

**db/**  
Handles the MongoDB database connection.

**server.js**  
Main entry point of the application. It configures Express, middleware, routes, database connection, and the server port.

---

## ⚙️ Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/yashmarviya99/node_pr6-blog.git
```

### 2. Open the Project

```bash
cd node_pr6-blog
```

### 3. Install Dependencies

```bash
npm install
```

### 4. Start MongoDB

Make sure your local MongoDB server is running.

The project uses the following MongoDB database configuration:

```env
MONGO_URI=mongodb://127.0.0.1:27017/blogDB
```

### 5. Configure `.env`

Create a `.env` file in the project root:

```env
PORT=5000
MONGO_URI=mongodb://127.0.0.1:27017/blogDB
```

> Do not upload your `.env` file to GitHub if it contains private credentials.

### 6. Run the Project

The project uses Nodemon:

```bash
npm start
```

The server runs on:

```text
http://localhost:5000
```

---

## 🏠 Home API

### GET `/`

**URL:**

```text
http://localhost:5000/
```

**Response:**

```json
{
  "message": "Blog api is running"
}
```

---

# 📚 Blog API Endpoints

Base URL:

```text
http://localhost:5000/api/blogs
```

| Method | Endpoint | Description |
|---|---|---|
| POST | `/api/blogs` | Create a new blog |
| GET | `/api/blogs` | Get all blogs |
| GET | `/api/blogs/:id` | Get one blog |
| PUT | `/api/blogs/:id` | Update a blog |
| DELETE | `/api/blogs/:id` | Delete a blog |

---

## 1️⃣ Create Blog

**Method:** `POST`

**URL:**

```text
http://localhost:5000/api/blogs
```

### Request Body

```json
{
  "title": "Advanced Node.js",
  "author": "Yash",
  "content": "Updated Node.js blog content.",
  "category": "Backend"
}
```

### Response

```json
{
  "message": "Blog Created Successfully",
  "data": {
    "_id": "BLOG_ID",
    "title": "Advanced Node.js",
    "author": "Yash",
    "content": "Updated Node.js blog content.",
    "category": "Backend"
  }
}
```

---

## 2️⃣ Get All Blogs

**Method:** `GET`

**URL:**

```text
http://localhost:5000/api/blogs
```

This API returns all blog documents stored in MongoDB.

---

## 3️⃣ Get Single Blog

**Method:** `GET`

**URL:**

```text
http://localhost:5000/api/blogs/:id
```

Example:

```text
http://localhost:5000/api/blogs/6ac34d734c786d968a6dd26c
```

Replace the ID with an actual MongoDB blog ID.

---

## 4️⃣ Update Blog

**Method:** `PUT`

**URL:**

```text
http://localhost:5000/api/blogs/:id
```

Example request body:

```json
{
  "title": "Advanced Node.js Updated",
  "author": "Yash",
  "content": "Updated content of the Node.js blog.",
  "category": "Backend"
}
```

The API uses the blog ID to find the existing document and update its data.

---

## 5️⃣ Delete Blog

**Method:** `DELETE`

**URL:**

```text
http://localhost:5000/api/blogs/:id
```

Example:

```text
http://localhost:5000/api/blogs/6ac34d734c786d968a6dd26c
```

Replace the ID with the blog ID you want to delete.

---

# 🗃️ Blog Schema

The Blog model contains these fields:

| Field | Type | Required |
|---|---|---|
| title | String | Yes |
| author | String | Yes |
| content | String | Yes |
| category | String | Yes |
| createdAt | Date | Automatically added |
| updatedAt | Date | Automatically added |

The schema uses Mongoose timestamps, so `createdAt` and `updatedAt` are automatically managed.

---

# 🧪 Testing with Postman

You can test all CRUD APIs using Postman.

### Create

```text
POST /api/blogs
```

### Read All

```text
GET /api/blogs
```

### Read One

```text
GET /api/blogs/:id
```

### Update

```text
PUT /api/blogs/:id
```

### Delete

```text
DELETE /api/blogs/:id
```

For POST and PUT requests, select:

```text
Body → raw → JSON
```

Then provide the JSON request body.

---

## 🔄 CRUD Flow

```text
CREATE  → POST
READ    → GET
UPDATE  → PUT
DELETE  → DELETE
```

---

## 🔐 Environment Variables

The project uses `dotenv` to load environment variables.

Example:

```env
PORT=5000
MONGO_URI=mongodb://127.0.0.1:27017/blogDB
```

The `.env` file is excluded from Git using `.gitignore`.

---

## 📦 Main Dependencies

```text
express
mongoose
dotenv
cors
```

### Development Dependency

```text
nodemon
```

---

## 🎯 Project Objective

The main objective of this project is to understand how to build a backend REST API using:

- Node.js
- Express.js
- MongoDB
- Mongoose
- MVC-style project structure
- REST API methods
- CRUD operations
- Middleware
- Database connection
- Postman API testing

---

## 👨‍💻 Author

**Yash**

---

## 🔗 Project Links

**GitHub:**  
https://github.com/yashmarviya99/node_pr6-blog.git

**Project Video:**  
https://drive.google.com/drive/folders/1TburdB_QcmBOnovONcRAj5gCM2euKWbW

---

## 📄 License

This project is created for educational/project purposes.
