A debounce is a higher-order function, which is a function that returns another function. 
This is done to form a closure around the `callback` and `wait` function parameters and the timeout variable so that their values are preserved.

It's a strategy that lets us improve performance by waiting until a certain amount of time has passed before triggering an event. 
When the user stops triggering the event, our code will run.

*Spread operator is used to spread the `args`. Why?* 

The function being returned from debounce() is supposed to act exactly the same as the function being provided, except for the fact that we're limiting how often it gets called. This means that if the original function was supposed to take two parameters, the returned function should too.

Whenever the wrapped function is triggered, two things happen:

1.  We cancel any pre-existing timeout   
2.  We schedule a new timeout, based on the amount of time indicated by the  `wait`  argument. When the timeout expires, we call our  `callback`  function and feed it whatever arguments we have, with the spread operator.

```
const debounce = (callback, wait) => {
  let timeoutId = null;
  
  return (...args) => {
    // clear any existing timeout
    clearTimeout(timeoutId);
    
    timeoutId = setTimeout(() => {
      callback(...args);
    }, wait);
  };
}
```

References:

 1. https://www.joshwcomeau.com/snippets/javascript/debounce/
 2. https://levelup.gitconnected.com/debounce-in-javascript-improve-your-applications-performance-5b01855e086
 3. https://stackoverflow.com/questions/65229032/js-what-are-the-args-in-a-debounce-function/65229092#65229092
