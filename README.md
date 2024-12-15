# Wildcard Route Issue in React Router

This repository demonstrates a subtle bug in React Router v6 where a wildcard route (`/*`) fails to match after a redirect from a nested route.  The issue arises when navigating to a path that doesn't match any explicit routes and a nested redirect is involved. This can be easily missed when building complex routing structures.

## Steps to Reproduce

1. Clone this repository.
2. Run `npm install`.
3. Run `npm start`.
4. Navigate to the `/about` route.
5. Click the link to go to a non-existent route (e.g., `/random`).

Expected Behavior: The wildcard route `/` should match and display the "404 Not Found" component. 
Actual Behavior: The application appears to hang or does not redirect to the wildcard route.

## Solution

The solution involves restructuring the nested routes or adding an explicit catch-all route as the first route in your `Routes`.