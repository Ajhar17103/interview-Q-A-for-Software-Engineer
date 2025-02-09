# JavaScript, React, and Next.js Interview Questions

## JavaScript

### 1. Closures
A closure is formed when a function is defined inside another function, and the inner function has access to the variables of the outer function, even after the outer function has returned.

### 2. Promises
A Promise represents the eventual completion or failure of an asynchronous operation and its resulting value.
- **States:** Pending, Fulfilled, Rejected
- **Methods:** `.then()`, `.catch()`, `.finally()`
- **Advantages:** Avoids callback hell, enables chaining

### 3. Async/Await
Syntactic sugar over Promises that makes asynchronous code look synchronous.
- `async` marks a function as asynchronous.
- `await` pauses execution until a Promise resolves.

### 4. Event Loop
JavaScript's mechanism for handling asynchronous operations non-blockingly using the **Call Stack**, **Event Queue**, and **Event Loop**.

### 5. Prototype & Prototypal Inheritance
JavaScript objects inherit properties and methods from other objects through prototypes.

### 6. Memoization
Optimization technique for caching results of expensive function calls.

### 7. Event Delegation
Instead of adding event listeners to multiple child elements, attach a single event listener to a parent element.

### 8. `this` Keyword
- Global Context: `this` refers to the global object.
- Object Method: `this` refers to the calling object.
- Arrow Functions: `this` is lexically inherited.

### 9. Differences
- `null` vs `undefined`: `null` is explicitly assigned; `undefined` means uninitialized.
- Deep Copy vs Shallow Copy: Shallow copy copies references; deep copy creates independent clones.

### 10. JavaScript Modules
Encapsulation of reusable code using `import` and `export`.

### 11. Function Methods
- `call()`: Calls a function with a specific `this` and arguments.
- `apply()`: Similar to `call()`, but takes arguments as an array.
- `bind()`: Returns a new function with a specific `this`.

### 12. Event Bubbling vs Capturing
- Bubbling: Events propagate from target to root.
- Capturing: Events propagate from root to target.

### 13. Debounce & Throttle
- **Debounce:** Delays execution until after a set time.
- **Throttle:** Ensures execution at most once per interval.

### 14. WeakMap & WeakSet
- **WeakMap:** Key-value pairs where keys are objects.
- **WeakSet:** Stores unique objects.

### 15. JavaScript Optimization
- Garbage Collection (GC) using **Mark-and-Sweep Algorithm**
- **V8 Optimizations**: Inline Caching, Ignition Interpreter, TurboFan Compiler

---


A collection of useful JavaScript functions for common programming problems.

## 1. Find Longest Word in a Sentence
```javascript
function longestWord(sentence) {
    return sentence.split(' ').reduce((longest, word) => word.length > longest.length ? word : longest, "");
}
```

## 2. Check if a String is a Palindrome
```javascript
function isPalindrome(str) {
    return str === str.split('').reverse().join('');
}
```

## 3. Remove Duplicates from an Array
```javascript
function removeDuplicates(arr) {
    return [...new Set(arr)];
}
```

## 4. Reverse a String Without Built-in Method
```javascript
function reverseString(str) {
    let reversed = "";
    for (let char of str) {
        reversed = char + reversed;
    }
    return reversed;
}
```

## 5. Max Count of Consecutive 1’s in an Array
```javascript
function maxConsecutiveOnes(arr) {
    return Math.max(...arr.join('').split('0').map(ones => ones.length));
}
```

## 6. Factorial of a Number
```javascript
function factorial(n) {
    return n <= 1 ? 1 : n * factorial(n - 1);
}
```

## 7. Merge and Sort Two Sorted Arrays
```javascript
function mergeSortedArrays(arr1, arr2) {
    return [...arr1, ...arr2].sort((a, b) => a - b);
}
```

## 8. Check if Every Value in arr1 has Its Square in arr2
```javascript
function hasCorrespondingSquares(arr1, arr2) {
    let map1 = arr1.reduce((acc, num) => (acc[num] = (acc[num] || 0) + 1, acc), {});
    let map2 = arr2.reduce((acc, num) => (acc[num] = (acc[num] || 0) + 1, acc), {});
    return Object.keys(map1).every(num => map2[num ** 2] === map1[num]);
}
```

## 9. Check if One String Can Be Formed by Rearranging Another (Anagram)
```javascript
function isAnagram(str1, str2) {
    return str1.split('').sort().join('') === str2.split('').sort().join('');
}
```

## 10. Get Unique Objects from an Array
```javascript
function uniqueObjects(arr) {
    let seen = new Set();
    return arr.filter(obj => !seen.has(obj.name) && seen.add(obj.name));
}
```

## 11. Find Maximum Number in an Array
```javascript
function findMax(arr) {
    return Math.max(...arr);
}
```

## 12. Return Only Even Numbers from an Array
```javascript
function filterEvenNumbers(arr) {
    return arr.filter(num => num % 2 === 0);
}
```

## 13. Check if a Number is Prime
```javascript
function isPrime(num) {
    if (num < 2) return false;
    for (let i = 2; i <= Math.sqrt(num); i++) {
        if (num % i === 0) return false;
    }
    return true;
}
```

## 14. Find Largest Element in a Nested Array
```javascript
function findLargestInNestedArray(arr) {
    return Math.max(...arr.flat(Infinity));
}
```

## 15. Fibonacci Sequence Up to n Terms
```javascript
function fibonacci(n) {
    let fib = [0, 1];
    for (let i = 2; i < n; i++) {
        fib[i] = fib[i - 1] + fib[i - 2];
    }
    return fib.slice(0, n);
}
```

## 16. Count Occurrences of Each Character in a String
```javascript
function countCharacters(str) {
    return str.split('').reduce((acc, char) => (acc[char] = (acc[char] || 0) + 1, acc), {});
}
```

## 17. Sort an Array in Ascending Order
```javascript
function sortAscending(arr) {
    return arr.sort((a, b) => a - b);
}
```

## 18. Sort an Array in Descending Order
```javascript
function sortDescending(arr) {
    return arr.sort((a, b) => b - a);
}
```

## 19. Reverse Words in a Sentence Without reverse()
```javascript
function reverseWords(sentence) {
    let words = sentence.split(' ');
    let reversed = [];
    for (let i = words.length - 1; i >= 0; i--) {
        reversed.push(words[i]);
    }
    return reversed.join(' ');
}
```

## 20. Flatten a Nested Array
```javascript
function flattenArray(arr) {
    return arr.flat(Infinity);
}
```

## 21. Convert String Input into an Object
```javascript
function stringToObject(path, value) {
    return path.split('.').reduceRight((acc, key) => ({ [key]: acc }), value);
}
```



## React

### 1. React Virtual DOM
Efficiently updates the UI by reconciling changes using **Fiber Algorithm**.

### 2. Optimization Techniques
- `React.memo()`, `useMemo()`, `useCallback()`
- Avoid unnecessary re-renders
- Use **Suspense** and **Concurrent Mode**

### 3. `useEffect` vs `useLayoutEffect`
- `useEffect()`: Runs asynchronously after render.
- `useLayoutEffect()`: Runs synchronously after DOM updates.

### 4. Server vs Client Components
- **Server Components:** No client-side JS, better performance.
- **Client Components:** Handles UI interactivity.

### 5. Hydration
Attaching event listeners to SSR-rendered content to maintain interactivity.

### 6. React Event Delegation
Uses Synthetic Events to optimize performance.

### 7. Memory Leaks Prevention
- Clean up subscriptions (`setInterval`, `useEffect` cleanup)
- Remove event listeners when unmounting

---

## Next.js

### 1. Static vs Server Rendering
- **Static Generation (SSG):** Pre-renders pages at build time.
- **Server-Side Rendering (SSR):** Renders pages dynamically on request.

### 2. Incremental Static Regeneration (ISR)
Updates static pages without rebuilding the entire site.

### 3. API Routes
Functions that run on the server inside the `/api` directory.

### 4. `getStaticProps` vs `getServerSideProps`
- `getStaticProps()`: Fetches data at build time.
- `getServerSideProps()`: Fetches data on every request.

### 5. Dynamic Routing
Uses file-based routing with square brackets (`[id].js`).

### 6. Next.js Image Optimization
Uses `next/image` to optimize and lazy-load images.

### 7. Performance Optimizations
- Lazy Loading Components (`React.lazy`, `Suspense`)
- **Virtualization** for large lists (`react-window`)
- **Automatic Batching** in React 18

---

## Authentication

### 1. `localStorage` vs `sessionStorage`
- `localStorage`: Persistent storage across sessions.
- `sessionStorage`: Data expires when the session ends.

### 2. WebAuthn & Passkeys
Passwordless authentication using biometrics or security keys.

### 3. CSRF Prevention
- Use **SameSite Cookies** (`Strict` or `Lax`).
- Implement **CSRF tokens**.
- Use **CORS preflight checks**.

### 4. Authentication in SSR vs SPA
- **SPA:** Uses JWTs, stored in `localStorage`.
- **SSR:** Uses HTTP-only cookies, more secure.


