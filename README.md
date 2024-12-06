# React UseEffect setInterval Memory Leak

This repository demonstrates a common bug in React applications: memory leaks caused by improper use of the `setInterval` function within the `useEffect` hook.

## Bug Description
The `bug.js` file contains a React component that uses `setInterval` to update a counter every second.  However, it fails to include a cleanup function in the `useEffect` hook to stop the interval when the component unmounts. This leads to a memory leak because the interval continues to run even after the component is no longer needed.

## Solution
The `bugSolution.js` file shows the correct way to use `setInterval` within `useEffect`. It includes a cleanup function that uses `clearInterval` to stop the interval when the component is unmounted, preventing the memory leak.

## How to reproduce
1. Clone this repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe that the count continuously increments even if you navigate away from the page or refresh it (the memory leak).
5. Review the `bugSolution.js` file for a corrected implementation.
