# Task Management API

This is a simple **Task Management API** built using **Node.js**, **Express**, and **MongoDB**. It allows users to perform CRUD operations on tasks, including creating, reading, updating, and deleting tasks.

## Features
- Add a new task with a title and description.
- View all tasks.
- View a specific task by its ID.
- Update the status of a task.
- Delete a task.

## Requirements
To run this project, you need the following installed:
- [Node.js](https://nodejs.org/)
- [MongoDB Atlas Account](https://www.mongodb.com/cloud/atlas) (or a local MongoDB instance)

## Setup

1. **Clone the Repository:**
```bash
git clone https://github.com/Amit1198911/Todo-API.git
cd https://github.com/Amit1198911/Todo-API.git
```

2. **Install Dependencies:**
```bash
npm install
```

3. **Configure MongoDB Connection:**
   Update the `mongoose.connect()` URI in the code with your MongoDB connection string:
   ```javascript
   mongoose.connect("<your-mongodb-connection-string>", {
     useNewUrlParser: true,
     useUnifiedTopology: true,
     tls: true,
   });
   ```

4. **Run the Server:**
```bash
node server.js
```
   The server will run on `http://localhost:5000` by default.

## API Endpoints

### **1. POST /tasks**
Create a new task.
- **Request Body:**
  ```json
  {
    "title": "Task Title",
    "description": "Task Description"
  }
  ```
- **Response:**
  ```json
  {
    "_id": "<task-id>",
    "title": "Task Title",
    "description": "Task Description",
    "status": "pending",
    "__v": 0
  }
  ```

### **2. GET /tasks**
Fetch all tasks.
- **Response:**
  ```json
  [
    {
      "_id": "<task-id>",
      "title": "Task Title",
      "description": "Task Description",
      "status": "pending",
      "__v": 0
    }
  ]
  ```

### **3. GET /tasks/:id**
Fetch a specific task by its ID.
- **Response:**
  ```json
  {
    "_id": "<task-id>",
    "title": "Task Title",
    "description": "Task Description",
    "status": "pending",
    "__v": 0
  }
  ```

### **4. PUT /tasks/:id**
Update the status of a task.
- **Request Body:**
  ```json
  {
    "status": "in-progress"
  }
  ```
- **Response:**
  ```json
  {
    "_id": "<task-id>",
    "title": "Task Title",
    "description": "Task Description",
    "status": "in-progress",
    "__v": 0
  }
  ```

### **5. DELETE /tasks/:id**
Delete a task by its ID.
- **Response:**
  ```json
  {
    "message": "Task deleted successfully"
  }
  ```

## Project Structure
```
.
├── server.js          # Main server file
├── package.json       # Dependencies and scripts
├── README.md          # Project documentation
```

## Technologies Used
- **Node.js**: Backend runtime environment.
- **Express.js**: Web framework for Node.js.
- **MongoDB Atlas**: Cloud-hosted database.
- **Mongoose**: ODM library for MongoDB.
- **Body-Parser**: Middleware for parsing JSON.
- **Cors**: Middleware for handling cross-origin requests.

## Troubleshooting
- Ensure your MongoDB Atlas cluster is running and the connection string is correct.
- Check that your IP is whitelisted in MongoDB Atlas (**Network Access** settings).

## License
This project is open-source and available under the [MIT License](LICENSE).
