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


