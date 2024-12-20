# RestfulDemo

RestfulDemo is a simple project that demonstrates the basic principles of a RESTful API. It integrates a **C# backend** (built with ASP.NET Core Web API) and a **Node.js frontend** (using Express.js) to perform basic task management. The project showcases the communication between two technologies via standard HTTP methods.

## Project Structure

The project consists of two parts:

1. **Backend (C#)** - A RESTful API to manage tasks.
2. **Frontend (Node.js)** - A server that interacts with the backend API and exposes endpoints for clients.

---

## Backend (C# with ASP.NET Core)

### Folder: `RestfulDemoBackend/TaskApi`

### Overview
The backend provides two primary endpoints:
- `GET /task`: Retrieves a list of tasks.
- `POST /task`: Adds a new task to the list.

### File Structure

```
RestfulDemoBackend/
├── TaskApi/
    ├── Controllers/
        └── TaskController.cs
    ├── Program.cs
    ├── Startup.cs
    └── TaskApi.csproj
```

### Key File: `Controllers/TaskController.cs`
This file contains the logic for handling HTTP requests related to tasks.

#### Endpoints:
1. **GET /task**
   - Fetches the current list of tasks.
   - Example Response:
     ```json
     [
         "Learn REST",
         "Build API"
     ]
     ```

2. **POST /task**
   - Adds a new task to the list.
   - Request Body:
     ```json
     "New Task"
     ```
   - Example Response (after adding):
     ```json
     [
         "Learn REST",
         "Build API",
         "New Task"
     ]
     ```

#### Key Features:
- **Static In-Memory List**: Simulates a database.
- **Validation**: Ensures tasks are not empty.
- **HTTP Methods**: Demonstrates RESTful conventions (`GET` and `POST`).

---

## Frontend (Node.js with Express.js)

### Folder: `RestfulDemoFrontend`

### Overview
The frontend acts as a middle layer between the client and the backend. It consumes the backend API and provides its own endpoints for task management.

### File Structure

```
RestfulDemoFrontend/
├── server.js
├── package.json
└── package-lock.json
```

### Key File: `server.js`
This file contains the Node.js application that exposes two endpoints:

#### Endpoints:
1. **GET /tasks**
   - Fetches tasks from the backend (`http://localhost:5000/task`).
   - Example Response:
     ```json
     [
         "Learn REST",
         "Build API"
     ]
     ```

2. **POST /tasks**
   - Sends a new task to the backend.
   - Request Body:
     ```json
     "A new task"
     ```
   - Example Response (after adding):
     ```json
     [
         "Learn REST",
         "Build API",
         "A new task"
     ]
     ```

#### Key Features:
- **HTTP Requests via Axios**: Communicates with the backend API.
- **Express.js for Routing**: Handles client requests.
- **Body Parsing**: Processes JSON payloads using `body-parser`.

---

## How It Works

1. **Client Interaction**:
   - The client interacts with the frontend endpoints (e.g., `/tasks`).

2. **Frontend Role**:
   - The frontend server forwards requests to the backend API (`http://localhost:5000/task`).

3. **Backend Role**:
   - The backend processes the request (e.g., retrieving or adding tasks) and returns the appropriate response.

4. **Response Flow**:
   - The backend response is forwarded to the client by the frontend server.

---

## Running the Project

### Prerequisites
- **.NET SDK** (for the backend): [Download](https://dotnet.microsoft.com/)
- **Node.js** (for the frontend): [Download](https://nodejs.org/)
- **VS Code** (optional): [Download](https://code.visualstudio.com/)

### Setup

#### Backend Setup
1. Navigate to the backend folder:
   ```bash
   cd RestfulDemoBackend/TaskApi
   ```
2. Run the API:
   ```bash
   dotnet run
   ```
3. Test the backend:
   - **GET /task**: Visit `http://localhost:5000/task` in your browser.
   - **POST /task**: Use Postman or `curl` to add tasks.

#### Frontend Setup
1. Navigate to the frontend folder:
   ```bash
   cd RestfulDemoFrontend
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Start the frontend server:
   ```bash
   node server.js
   ```
4. Test the frontend:
   - **GET /tasks**: Visit `http://localhost:3000/tasks` in your browser.
   - **POST /tasks**: Use Postman or `curl` to add tasks.

---

## Example Interaction

1. **Fetch Tasks**:
   - Request: `GET http://localhost:3000/tasks`
   - Response:
     ```json
     [
         "Learn REST",
         "Build API"
     ]
     ```

2. **Add a Task**:
   - Request: `POST http://localhost:3000/tasks`
     ```json
     "Practice Integration"
     ```
   - Response:
     ```json
     [
         "Learn REST",
         "Build API",
         "Practice Integration"
     ]
     ```

---

## Key Learnings

- **RESTful API Principles**: Statelessness, resource-based design, and standard HTTP methods.
- **C# Backend**: Building APIs with ASP.NET Core.
- **Node.js Frontend**: Creating a server to consume and relay APIs.
- **Integration**: Communication between two technologies using HTTP.

---

## Future Enhancements
- **Database Integration**: Use a database like SQLite or MongoDB for persistent storage.
- **UI Layer**: Add a React or plain HTML/CSS frontend for a better user experience.
- **Additional Endpoints**: Implement `PUT` and `DELETE` operations for full CRUD functionality.
- **Error Handling**: Improve error logging and validation.

---

Enjoy exploring the principles of REST with **RestfulDemo**!

