---
title: "Todo App"
description: "A simple todo application using our library"
author: "Documentation Team"
date: "2024-01-25"
tags: ["todo", "example", "basic"]
---

# Todo App

A simple todo application that demonstrates basic CRUD operations with our library.

## What We'll Build

A todo app that can:
- Add new todos
- Mark todos as complete
- Delete todos
- Filter todos by status

## Project Structure

```
todo-app/
├── package.json
├── server.js
├── public/
│   ├── index.html
│   ├── style.css
│   └── app.js
└── todos.json
```

## Step 1: Setup

Create the project structure:

```bash
mkdir todo-app
cd todo-app
npm init -y
npm install our-library express
```

## Step 2: Server Code

Create `server.js`:

```javascript
import express from 'express';
import { Library } from 'our-library';
import fs from 'fs/promises';

const app = express();
const lib = new Library();

app.use(express.json());
app.use(express.static('public'));

// Load todos
let todos = [];

// API Routes
app.get('/api/todos', (req, res) => {
  res.json(todos);
});

app.post('/api/todos', (req, res) => {
  const todo = {
    id: Date.now(),
    text: req.body.text,
    completed: false
  };
  todos.push(todo);
  res.json(todo);
});

app.put('/api/todos/:id', (req, res) => {
  const todo = todos.find(t => t.id == req.params.id);
  if (todo) {
    todo.completed = req.body.completed;
    res.json(todo);
  } else {
    res.status(404).json({ error: 'Todo not found' });
  }
});

app.delete('/api/todos/:id', (req, res) => {
  todos = todos.filter(t => t.id != req.params.id);
  res.json({ success: true });
});

app.listen(3000, () => {
  console.log('Todo app running on http://localhost:3000');
});
```

## Step 3: Frontend

Create `public/index.html`:

```html
<!DOCTYPE html>
<html>
<head>
    <title>Todo App</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container">
        <h1>Todo App</h1>
        <form id="todo-form">
            <input type="text" id="todo-input" placeholder="Add a new todo">
            <button type="submit">Add</button>
        </form>
        <ul id="todo-list"></ul>
    </div>
    <script src="app.js"></script>
</body>
</html>
```

## Step 4: Run the App

```bash
node server.js
```

Visit `http://localhost:3000` to see your todo app!

## Key Features Demonstrated

- RESTful API design
- Frontend-backend communication
- Data persistence
- User interface interactions

## Next Steps

Try adding features like:
- Todo categories
- Due dates
- Search functionality
- User authentication 