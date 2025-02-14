# React useEffect Hook Memory Leak with setInterval

This repository demonstrates a common mistake when using the `useEffect` hook in React with `setInterval`.  Forgetting to return a cleanup function from `useEffect` can lead to memory leaks and unexpected behavior.

## Bug
The `bug.js` file contains a component that uses `setInterval` to update a counter every second. However, it's missing a cleanup function to clear the interval when the component unmounts or when the dependency array changes.  This will cause the interval to continue running even after the component is no longer needed, resulting in a memory leak.

## Solution
The `bugSolution.js` file provides the corrected code.  It includes a cleanup function that uses `clearInterval` to stop the interval when it's no longer required, preventing memory leaks.