# Node.js Server Hanging Issue

This repository demonstrates a common issue in Node.js where a long-running task within the request handler blocks the event loop, causing the server to hang and become unresponsive to new requests.  The `server.js` file contains the buggy code, while `server-solution.js` provides a solution using asynchronous operations to prevent blocking.

## Bug
The bug is in the `server.js` file. The `while` loop simulates a long-running task that takes 5 seconds to complete. During this time, the event loop is blocked, and the server cannot handle any new incoming requests.

## Solution
The `server-solution.js` file demonstrates a solution using asynchronous operations with `setTimeout` to prevent blocking.  The long-running task is offloaded to a separate execution context, allowing the event loop to remain responsive.