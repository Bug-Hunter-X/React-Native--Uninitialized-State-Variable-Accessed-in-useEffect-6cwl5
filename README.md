# React Native: Uninitialized State Variable in useEffect

This repository demonstrates a common error in React Native: accessing a state variable before it's initialized within a `useEffect` hook.  The error typically manifests as `undefined` is not an object (evaluating 'count').

## Problem

The `bug.js` file shows the problem.  Attempting to access the `count` state variable inside the `useEffect` hook before the component has rendered will result in an error.  This is because `useState` hasn't populated the variable yet when the effect runs with an empty dependency array.

## Solution

The `bugSolution.js` file offers two solutions:

1. **Optional Chaining:**  Safely access the state variable using optional chaining (`?.`). This prevents the error if the variable is undefined.
2. **Initial State Value:** Set an initial value for the state variable to avoid `undefined`.