# Undefined req.body in Express.js POST Request

This repository demonstrates a common issue in Express.js where the `req.body` object is undefined in a POST request handler.  The issue arises when the necessary middleware to parse the request body is missing or incorrectly configured.

## Problem

The provided `bug.js` code attempts to access `req.body` in a POST request handler. However, because the `express.json()` middleware is improperly configured or missing, `req.body` remains undefined, leading to errors or unexpected behavior.

## Solution

The `bugSolution.js` file shows the corrected code. The `express.json()` middleware is correctly added to parse JSON request bodies.  This ensures that the `req.body` object is correctly populated with the data from the POST request.

## How to Reproduce

1. Clone this repository.
2. Navigate to the directory.
3. Run `npm install` to install Express.js
4. Run `node bug.js`.
5. Send a POST request to `http://localhost:3000/user` with a JSON payload (e.g., using Postman or curl).
6. Observe that the server logs an empty object for `req.body`.
7. Then run `node bugSolution.js` and repeat step 5. Observe that the server now correctly logs the JSON payload.