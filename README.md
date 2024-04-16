# Creating-an-API-using-Node.js

// Import required modules
const express = require('express');

// Create an Express application
const app = express();
const PORT = 3000; // Set the port for the server

// Middleware to parse JSON request bodies
app.use(express.json());

// Define routes
// GET request to the root route
app.get('/', (req, res) => {
  res.send('Hello, this is your API!');
});

// Example route to handle GET requests to /api/users
app.get('/api/users', (req, res) => {
  // In a real-world application, you might fetch data from a database
  const users = [
    { id: 1, name: 'John Doe' },
    { id: 2, name: 'Jane Smith' },
  ];
  res.json(users);
});

// Example route to handle POST requests to /api/users
app.post('/api/users', (req, res) => {
  // In a real-world application, you would process the request body and store data in a database
  console.log(req.body);
  res.status(201).send('User created successfully!');
});

// Start the server
app.listen(PORT, () => {
  console.log(`Server is running on http://localhost:${PORT}`);
});
