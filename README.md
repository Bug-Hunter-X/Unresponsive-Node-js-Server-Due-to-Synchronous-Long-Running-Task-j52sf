# Unresponsive Node.js Server

This repository demonstrates a common issue in Node.js where a long-running synchronous operation in a request handler blocks the event loop, causing the server to become unresponsive. The `server.js` file contains the buggy code, while `serverSolution.js` provides a corrected version using asynchronous operations.

## Problem

The original code simulates a long-running task (5-second delay) within the request handler. This blocks the event loop, preventing the server from handling other requests during this time.  Attempts to access the server will time out.

## Solution

The solution uses asynchronous techniques (e.g., `setTimeout`) to prevent blocking.  The long-running operation is moved to an asynchronous task, allowing the event loop to continue processing other requests even while the task is executing.  This prevents the server from becoming unresponsive.