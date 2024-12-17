# Stale Closures in React's useEffect Hook
This example demonstrates a common issue in React applications involving stale closures within the `useEffect` hook when used with `setInterval`.  The problem arises because the callback function passed to `setInterval` captures the initial value of `count`, leading to incorrect updates.

## Problem
The counter might not increment correctly because the `setInterval` callback uses a stale closure of the `count` variable.  Each time the interval fires, it adds 1 to the previous value it captured initially, not the current value of state.

## Solution
The solution involves using the functional update form of `setCount` to ensure that the counter always updates with the latest state value.