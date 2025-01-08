# React setInterval Memory Leak
This repository demonstrates a common mistake when using setInterval within a React component's useEffect hook, leading to a memory leak.  The bug occurs because the setInterval is not properly cleaned up when the component unmounts, causing the interval to continue running indefinitely even after the component is removed from the DOM.  The solution demonstrates how to fix this issue using the cleanup function provided by useEffect.

## Bug
The `bug.js` file contains the buggy component. It utilizes `setInterval` to increment a counter every second but lacks the essential cleanup function in useEffect to stop the interval when the component is unmounted. This leads to the interval continuously running, even after the component is no longer needed, resulting in a memory leak.

## Solution
The `bugSolution.js` file provides the corrected component. The solution involves using the cleanup function returned by `useEffect` to call `clearInterval` when the component unmounts. This ensures that the interval is stopped, preventing memory leaks.

## How to reproduce
1. Clone this repository.
2. Navigate to the `bug` or `bugSolution` folder.
3. Open `index.html` in your browser. Observe the difference in memory usage between the buggy and fixed components using your browser's developer tools.