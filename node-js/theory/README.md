# NodeJS Theoretical

1. What is node js? Why prefer node js? What is event loop? How performance is achieved with NodeJS.

- Node.js was a technology built to solve a specific problem: deal with intense asynchronous input and output events
- Node.js is an open-source JavaScript based platform for server-side programming built on Chrome's V8 JavaScript engine
- Node.js is an extremely powerful server-side platform to develop modern, reliable and scalable web applications
- it’s event driven architecture is perfect for applications with intense I/O (Inputs and Outputs)
- Features: Scalable, Light, Fast, Performace, Simple, Community
- Non Blocking I/O: it makes it possible for a server to receive many requests without blocking the application while the response is being processed in the background.
- Single Thread on Front: Node.js can deal with many events at the same time with its single thread characteristic that delegates the asynchronous operations to a multi thread platform, which means that just one thread is able to handle inputs and outputs.
- Event Driven: the control flow of this server side platform is driven by the occurrence of events.
- Node Package Manager: the world's largest free and open source library of functionalities, and can be easily imported and used in any Node application
- No Buffering: Node.js applications never buffer data, which dramatically reduces the processing time of uploading files, such as videos or audios. In other words, it simply outputs data in chunks
- Scalable: high capacity of handling large amounts of requests asynchronously with low infrastructure by it’s architecture that operates on single thread combined with multi thread platform, allowing it receives thousands of simultaneous events

- NodeJS Architecture: 3 key things work together
1. Event queue
As soon as these requests reach the application, they go to the Event Queue, which is a queue where all the events that occur in the application goes first, and where they await to be sent to be processed in the main thread called Event Loop
2. Event loop
When a request (Blocking Operation) enters in the Event Loop, which is a single thread platform that runs the V8 Engine in its core to compile JavaScript, it’s delegated to the Thread Pool platform to be processed in background. So, with this architectural flow, the main thread is available again to handle other events.
3. Thread pool
In the Thread Pool, which is a multi thread platform that runs a library called libuv and has C++ in its core, the request (Blocking Operation) is processed asynchronously in the background until it’s completed and ready to be returned.
