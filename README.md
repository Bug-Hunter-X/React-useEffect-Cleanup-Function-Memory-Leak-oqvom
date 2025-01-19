# React useEffect Cleanup Function Memory Leak

This repository demonstrates a common React bug involving a missing `return` statement within the cleanup function of a `useEffect` hook.  This oversight can lead to memory leaks and unexpected behavior.

The `bug.js` file showcases the problematic code. The `bugSolution.js` file provides the corrected version.

## Problem

The original `useEffect` hook logs a message on component mount. However, it fails to properly clean up after itself when the component unmounts.  This lack of cleanup can cause resources (like event listeners or timers) to persist, leading to memory leaks.

## Solution

The corrected `useEffect` hook includes a `return` statement within the cleanup function. This ensures that any necessary cleanup actions (such as removing event listeners or clearing intervals) are performed when the component is unmounted, preventing memory leaks.
