In this implementation, the throttle function takes a function to be throttled and a delay time in milliseconds. 
It returns a new function that will execute the original function at most once per delay period. 
If the function is called again before the delay has passed, it is ignored. 

The throttle function takes two parameters: func, which is the function to be throttled, and duration, which is the time interval (in milliseconds) between function calls.

The function returns a new function that wraps the original func. This wrapped function checks whether the specified time interval (duration) has passed since the last time func was called. If it has, the wrapped function calls func with the arguments passed to it, and sets a flag (shouldWait) to prevent func from being called again until the time interval has elapsed.

If the wrapped function is called again before the time interval has elapsed, it does not call func again. Instead, it simply sets the shouldWait flag to true and schedules a setTimeout callback to reset the flag to false after the specified time interval has elapsed.

      function throttle(func, duration) {
        let shouldWait = false

        return function (...args) {
          if (!shouldWait) {
            func(...args);
            shouldWait = true

            setTimeout(() => {
              shouldWait = false
            }, duration)
          }
        }
      }

