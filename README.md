# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js servers where a long-running task blocks the event loop, causing unresponsiveness. The `server.js` file contains the problematic code, while `serverSolution.js` provides a solution using asynchronous operations.

## Problem

The original server code contains a `while` loop that simulates a 5-second delay. During this time, the server cannot process other requests, leading to significant delays and potential timeouts.  This is because Node.js uses a single-threaded event loop, and blocking operations halt the processing of other events.

## Solution

The solution leverages asynchronous operations to prevent blocking.  The updated code uses `setTimeout` to schedule the response after the 5-second delay without blocking the event loop. This approach ensures that the server remains responsive to other requests even while handling long-running tasks.