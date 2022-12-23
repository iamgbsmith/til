# Measure JavaScript Execution Time

__Category: JavaScript__

You can measure how long a call takes in JavaScript using timer methods.

For example:

```javascript 
console.time("some-operation");
callSomeFunction ();
console.timeLog("some-operation");
anotherFunction () ;
console.timeEnd("some-operation");
```

Output for timers is in seconds/milliseconds and timeLog will show the time in seconds since the timer was started.

Each timer should be given a unique label to differentiate from other timers.
