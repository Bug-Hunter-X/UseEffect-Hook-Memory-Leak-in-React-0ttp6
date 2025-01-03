# React useEffect Hook Memory Leak

This repository demonstrates a common mistake in using the `useEffect` hook in React: forgetting to include a cleanup function to prevent memory leaks.

The `bug.js` file contains the faulty code.  The `bugSolution.js` shows the corrected version.

## Problem:
The `setInterval` within the `useEffect` hook isn't cleared when the component unmounts. This leads to continued updates even after the component is no longer rendered, causing a memory leak.

## Solution:
The cleanup function, returned from `useEffect`, is responsible for canceling the `setInterval` when the component is unmounted.  This prevents the memory leak and ensures proper resource management.