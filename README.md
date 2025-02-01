# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: missing error handling for invalid input.  Specifically, the `/users/:id` route attempts to parse the `id` parameter as an integer but doesn't handle cases where the parameter is not a valid integer. This can lead to crashes or unexpected behavior.

The `bug.js` file contains the problematic code.  The `bugSolution.js` file demonstrates how to fix this issue by adding error handling and input validation.

## How to Reproduce the Bug

1. Clone the repository.
2. Run `npm install` to install the dependencies.
3. Run `node bug.js`.
4. Send a GET request to `/users/abc` (or any non-numeric ID).

You'll likely see an error because `parseInt('abc')` returns `NaN`, and the subsequent `user.id` check will fail.