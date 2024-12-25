# React Router Dom v6 Catch-all Route Issue

This repository demonstrates a common issue encountered when using catch-all routes ('/*') in React Router v6. The problem arises when the catch-all route unintentionally overrides other, more specific routes, preventing them from working as expected.

## Issue Description

The provided `App.js` demonstrates a scenario where a catch-all route (`/*`) is defined after more specific routes (`/` and `/about`).  While it appears that it should only match routes not matched by other routes, it is actually matched always. This behavior breaks other routes. 

The solution (`AppSolution.js`) illustrates the correct approach to using catch-all routes, ensuring that they only match if no other route matches first.

## How to reproduce

1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Observe that navigating to `/about` does not render the expected content.  This route is being caught by the catch-all route. 

## Solution

The correct way to resolve the issue is to place the catch-all route last.  This ensures that more specific routes are matched before the catch-all route is considered.