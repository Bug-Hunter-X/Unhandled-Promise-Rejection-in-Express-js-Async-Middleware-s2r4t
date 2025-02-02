# Unhandled Promise Rejection in Express.js Async Middleware

This repository demonstrates a common error in Node.js Express.js applications: unhandled promise rejections in asynchronous middleware.  The server doesn't respond appropriately when an error happens during an asynchronous operation.

## Bug

The `bug.js` file contains an Express.js app with an asynchronous middleware function (`someAsyncOperation`). This function has a 50% chance of throwing an error. The error handling within the middleware is incomplete.  The server logs the error, but doesn't send a proper response to the client.  This results in an unhandled promise rejection and the server may appear unresponsive.

## Solution

The `bugSolution.js` file provides a corrected version that uses a `try...catch` block within the `async` function to handle the potential error.  This ensures a proper error response is sent to the client, even if an error occurs during the asynchronous operation.