# Express.js Route Handler Missing Error Handling for Invalid User IDs

This repository demonstrates a common error in Express.js route handlers:  missing error handling for invalid input.  Specifically, the `/users/:id` route attempts to parse the `id` parameter as an integer but does not handle cases where the `id` is not a valid integer, potentially leading to application crashes or unexpected behavior.

## Bug

The `bug.js` file contains the erroneous code.  It attempts to find a user by ID, but it fails to handle cases where the ID is not a number, causing the `parseInt` function to return `NaN`. This results in an unsuccessful search for the user leading to either an error, a 404, or simply incorrect behaviour.

## Solution

The `bugSolution.js` file provides a corrected version of the code. It includes comprehensive error handling to check if the `userId` is a valid number. If it's not, it sends an appropriate error response.  This prevents unexpected behavior and improves application robustness.

## How to reproduce

1. Clone this repository.
2. Navigate to the directory.
3. Run `node bug.js` and try accessing `/users/abc` or `/users/123`.
4. Observe the difference with `node bugSolution.js` and then compare the results.