---
title: "Hello World"
description: "Build your first real application"
author: "Documentation Team"
date: "2024-01-22"
tags: ["hello-world", "tutorial", "example"]
---

# Hello World

Now that you've taken your first steps, let's build something more substantial - a real "Hello World" application!

## What We'll Build

We'll create a simple web application that:
- Displays a greeting
- Accepts user input
- Processes the input
- Shows the result

## Prerequisites

Make sure you've completed the [First Steps](./first-steps) guide before continuing.

## Step 1: Set Up the Project

Create a new directory and initialize it:

```bash
mkdir hello-world-app
cd hello-world-app
npm init -y
```

## Step 2: Install Dependencies

```bash
npm install our-library express
```

## Step 3: Create the Server

Create `server.js`:

```javascript
import express from 'express';
import { Library } from 'our-library';

const app = express();
const lib = new Library();

app.use(express.json());

app.get('/', (req, res) => {
  res.send(`
    <h1>Hello World!</h1>
    <form method="POST">
      <input name="message" placeholder="Enter your message">
      <button type="submit">Process</button>
    </form>
  `);
});

app.post('/', (req, res) => {
  const result = lib.process(req.body.message);
  res.send(`<h1>Result: ${result}</h1>`);
});

app.listen(3000, () => {
  console.log('Server running on http://localhost:3000');
});
```

## Step 4: Run Your Application

```bash
node server.js
```

Visit `http://localhost:3000` in your browser!

## What You've Learned

- How to create a web server
- How to handle user input
- How to process data with our library
- How to display results

## Next Steps

Ready for more complex applications? Check out our [Core Concepts Guide](./core-concepts)! 