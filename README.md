# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js: an unresponsive server caused by blocking the event loop.  The `server.js` file contains a simple HTTP server that simulates a long-running task, effectively halting the event loop and preventing it from processing new requests.

The solution, provided in `serverSolution.js`, utilizes asynchronous operations (using `setTimeout`) to prevent blocking and allow the server to remain responsive.

## How to Reproduce

1. Clone the repository.
2. Run `node server.js`. 
3. Attempt to access the server using a web browser or `curl`.  Note the significant delay or inability to connect after the initial request.
4. Run `node serverSolution.js` to see the corrected, responsive version. 

## Key Learning

This example highlights the critical importance of avoiding blocking operations in Node.js.  Always use asynchronous techniques (callbacks, Promises, async/await) for long-running tasks to prevent the event loop from freezing.