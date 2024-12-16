# React 19 useEffect Infinite Loop Bug

This repository demonstrates a common error in React 19 involving the `useEffect` hook that can lead to an infinite loop.  The issue arises from incorrectly attempting to update state within the dependency array of `useEffect`, causing the effect to run repeatedly, leading to a performance issue or a crash.

## Bug Description

The `bug.js` file contains a React component that uses `useEffect` to increment a counter. However, the state update `setCount(count + 1)` within the dependency array causes the `useEffect` hook to trigger repeatedly resulting in an infinite loop. The infinite loop is caused by not returning a cleanup function in the useEffect.  This leads to a continuous re-render and state update cycle.

## Solution

The `bugSolution.js` file provides a corrected version where the state update only occurs when a change is initiated from external sources. To solve the infinite loop, a cleanup function should be returned to break the chain and prevent the infinite rendering loop.