# React useEffect setInterval Memory Leak

This repository demonstrates a common React bug involving the improper use of `setInterval` within the `useEffect` hook.  Without proper cleanup, this leads to memory leaks and unpredictable component behavior.

The `bug.js` file contains the buggy code. The `bugSolution.js` file provides the corrected version.

## Bug
The primary issue is the absence of a cleanup function within the `useEffect` hook. This prevents the `setInterval` from being cleared when the component unmounts or when the dependencies change.

## Solution
The solution includes a return function within `useEffect`. This function is responsible for clearing the interval using `clearInterval` when the component is no longer needed. This prevents memory leaks and ensures the component behaves as expected.