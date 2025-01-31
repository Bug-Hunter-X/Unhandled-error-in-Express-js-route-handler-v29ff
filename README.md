# Unhandled Error in Express.js Route Handler

This repository demonstrates a common error in Express.js route handlers:  missing error handling for invalid user IDs.  The `bug.js` file shows the problematic code, while `bugSolution.js` provides the corrected version with robust error handling.

## Problem

The original code attempts to find a user based on an ID passed in the route parameters.  It lacks error handling for two scenarios:

1.  **Invalid User ID:** If the ID is not a number, `parseInt(userId)` will return `NaN`, leading to a failed search and a potential error.
2.  **User Not Found:** If no user matches the provided ID, the code will throw an error.

## Solution

The solution involves adding checks to handle both scenarios:

1.  **Type Check:** Verify that the ID is a number using `isNaN()`.
2.  **Existence Check:** Check if a user with the ID exists before sending the response.

By implementing proper error handling, you can prevent unexpected crashes and provide informative error messages to clients.