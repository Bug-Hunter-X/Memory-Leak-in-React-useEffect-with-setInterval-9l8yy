# React useEffect setInterval Memory Leak

This repository demonstrates a common bug in React applications involving the `useEffect` hook and `setInterval`.  The provided code snippet uses `setInterval` within a `useEffect` hook without proper cleanup, leading to memory leaks and unpredictable behavior.

The `bug.js` file contains the faulty code, showcasing the incorrect implementation. The `bugSolution.js` file provides the corrected version with a cleanup function.

## Problem

The `setInterval` function continues to run indefinitely without a way to stop it once the component unmounts or the effect is no longer needed. This causes memory leaks because the interval keeps running even after the component has been removed from the DOM.

## Solution

The solution involves returning a cleanup function from the `useEffect` callback. This cleanup function is responsible for clearing the interval using `clearInterval`.  This ensures the interval stops running when the component unmounts, preventing memory leaks.