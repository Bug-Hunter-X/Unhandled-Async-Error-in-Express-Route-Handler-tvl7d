# Unhandled Async Error in Express Route Handler

This repository demonstrates a common error in Express.js applications where an asynchronous operation within a route handler throws an error without proper error handling. This results in the application crashing silently without providing useful debugging information.

The `bug.js` file contains the problematic code, and `bugSolution.js` demonstrates how to fix the issue using try...catch blocks and proper error handling.

## How to Reproduce
1. Clone this repository
2. Run `npm install`
3. Run `node bug.js`
4. Try accessing `http://localhost:3000/` in your browser.  You'll see no response and the server will likely crash.
5. Run `node bugSolution.js` to see the corrected version in action.  This version will gracefully handle the error and return an appropriate error message to the client.

## Solution
The solution involves using `try...catch` blocks to handle potential errors within asynchronous operations and using `next(err)` to pass errors to Express's error handling middleware.