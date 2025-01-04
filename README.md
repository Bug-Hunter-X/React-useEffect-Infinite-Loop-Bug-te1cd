# React useEffect Infinite Loop

This repository demonstrates a common React bug involving the `useEffect` hook, which can lead to an infinite loop. The bug arises from the improper use of the dependency array in `useEffect`, causing the effect to run repeatedly, resulting in an infinite update cycle.

## Bug Description

The `MyComponent` uses the `useEffect` hook to update a count state. However, because of the incorrect dependency array `[count]`, the effect is triggered every time the count changes, leading to an infinite loop. Each execution increments the count, triggering another re-render and thus another execution of the useEffect. This causes the application to become unresponsive and potentially crash.

## Solution

The solution involves fixing the dependency array in the `useEffect` hook. The correct dependency array should either be an empty array `[]`, meaning the effect runs only once after the initial render, or a different dependency that would allow controlled updates.