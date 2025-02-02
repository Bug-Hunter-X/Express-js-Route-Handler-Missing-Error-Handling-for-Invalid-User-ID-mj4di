# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers:  missing error handling for invalid input. Specifically, the `/users/:id` route attempts to parse the `id` parameter as an integer but doesn't handle the case where the parameter is not a valid integer, leading to potential crashes or unexpected behavior.

The `bug.js` file contains the buggy code. The `bugSolution.js` file provides a corrected version with proper error handling.

## Bug

The `bug.js` file shows a route handler that's vulnerable to crashes if a non-integer ID is passed. It uses `parseInt` to convert the parameter, but doesn't handle the case where `parseInt` returns `NaN`.

## Solution

The `bugSolution.js` file demonstrates a corrected version. It adds checks to ensure that the ID is a valid integer and that a user with that ID exists before attempting to access the user object.