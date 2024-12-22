# React Native useCallback Hook Stale Closure Issue

This repository demonstrates a common error when using the `useCallback` hook in React Native: stale closures due to missing state variables in the dependency array.

## Problem

The `useCallback` hook is intended to memoize functions, preventing unnecessary re-renders. However, if a function within `useCallback` depends on state variables, and those variables are not included in the dependency array, the function will not update when the state changes. This can lead to unexpected behavior and bugs.

## Solution

The solution is simple: include all state variables the function depends on in the dependency array of `useCallback`.

## How to reproduce

1. Clone the repository.
2. Run `npm install`.
3. Run `npx react-native run-android` (or the equivalent for your platform).
4. Observe the unexpected behavior: The counter will not increment correctly.
5. Uncomment the correct dependency array in `bugSolution.js` to fix the issue. 

This example highlights the importance of carefully managing dependencies when using `useCallback` to avoid subtle and difficult-to-debug errors.