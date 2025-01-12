# React useEffect Infinite Loop Bug

This repository demonstrates a common error in React's `useEffect` hook: creating an infinite loop by including a state variable in the dependency array that's modified within the effect itself.

## Bug Description
The `MyComponent` component uses `useState` and `useEffect` to display a click counter. However, because `count` (updated within the effect) is listed in the dependency array, this creates a loop that causes the component to rerender continuously.

## Solution
The solution involves removing the `count` dependency from the useEffect, if its not needed for running only once after the initial render.  Alternatively, if the count is actually needed in the dependency array, a proper logic should be implemented within the useEffect to avoid an infinite loop