# React useEffect setInterval Memory Leak
This example demonstrates a common error in React when using the `setInterval` function within the `useEffect` hook.  Failing to properly clear the interval leads to a memory leak, as the interval continues to run even after the component is unmounted. This is fixed by using the return value of useEffect to clear the interval before the component unmounts.

## Bug
The `bug.js` file contains the buggy component.  The `setInterval` function is used to update the counter every second, but there is no cleanup function to stop the interval when the component is unmounted.  This results in the interval continuing indefinitely, leading to a memory leak.

## Solution
The `bugSolution.js` file shows the corrected component. The `setInterval` function is now properly cleaned up using the return function of `useEffect`. This ensures that the interval is stopped when the component is unmounted, preventing the memory leak.