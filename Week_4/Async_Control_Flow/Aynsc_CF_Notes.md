# Asynchronous Control Flow Lecture

## Topics
- Asynchronous control flow
- setTimeout and setInterval functions
- Filesystem functions and their async nature
- Events and event handling, another asynchronous topics

### Async Flow
Asynchronous flow is important to avoid javascript blocking, in which lines of code are executed synchronously and have to wait for previous "block" or line of code to complete before running. This would be especially slow when thinking of a complex user interace. In asynchronous flow, it is important to be aware of the order of execution in order to understand how the code will run. 

**Order of Execution - order in which lines of codes will be executed

There are four parts of the Javascript engine that enable code to run at the same time based on a run-to-completion event loop:

- Call stack
- Web APIs
- Callback Queue
- Event Loop

![Javascript Event Loop](js-event-loop-explained.png)

1. Call Stack
- A mechanism for a code interpreter to keep track of its place in the script
- Functions are added to the call stack and then carried out

2. Web APIs
- examples include reading a network file, GET API request, lengthy tasks, connecting to chat server, timers/indicators for user
- Web APIs are added to a separate container after being pushed to the call stack until callback is triggered, in which the callback
is sent to the callback queue

3. Callback Queue
- A separate stack of callbacks that CAN be called in the future when javascript is ready to run them
- First in, first out order
- Callbacks are added to the event loop one after another AFTER the call stack completes the main thread/synchronous call stack

4. Event Loop
- Takes a function from the callback queue and runs them one after another to the call stack as it becomes possible to run them
- Consists of the call stack, Web API, and callback queue