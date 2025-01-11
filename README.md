# Express.js: Empty req.body on POST Request

This repository demonstrates a common issue in Express.js applications where the `req.body` object is empty when receiving JSON payloads from POST requests. The problem often stems from a missing or incorrectly configured body-parsing middleware.

## Bug Report

The `bug.js` file contains an Express.js application that attempts to log the incoming JSON data. However, despite sending a JSON payload in the POST request, `req.body` remains empty. This leads to unexpected behavior and prevents the application from properly processing the request data.

## Solution

The `solution.js` file shows the corrected code. By adding `app.use(express.json())` before the route handler, the application correctly parses the JSON payload, making `req.body` accessible and populated with the request data.

## How to Reproduce

1.  Clone this repository.
2.  Run `npm install express` to install the necessary dependencies.
3.  Run `node bug.js` to start the buggy application.
4.  Send a POST request to `http://localhost:3000/data` with a JSON payload (e.g., using curl or Postman).
5.  Observe that the console logs an empty object for `req.body`.
6.  Run `node solution.js` to start the corrected application and repeat the POST request.
7.  Observe that the console logs the correct JSON payload.