# React useEffect setInterval memory leak

This repository demonstrates a common React bug involving memory leaks caused by the improper use of `setInterval` within the `useEffect` hook.  The `bug.js` file showcases the problematic code, while `bugSolution.js` provides the corrected version.

## Bug Description

The original code uses `setInterval` to update a counter every second. However, it fails to include a cleanup function to `clearInterval` when the component unmounts. This leads to the interval continuing to run indefinitely, even after the component is no longer rendered, causing a memory leak.

## Solution

The solution involves adding a cleanup function within the `useEffect` hook's return statement. This function calls `clearInterval` with the interval ID, ensuring that the interval is properly cleared when the component is unmounted, preventing the memory leak.

## How to reproduce

1. Clone this repository
2. Run `npm install`
3. Run `npm start`
4. Observe the counter incrementing (bug.js)
5. Inspect the memory usage of the browser (observe the memory leak)
6. Run the fixed version in bugSolution.js and repeat steps 4 and 5 to check for improvement
