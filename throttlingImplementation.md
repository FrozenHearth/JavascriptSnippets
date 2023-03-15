In this implementation, the throttle function takes a function to be throttled and a delay time in milliseconds. 
It returns a new function that will execute the original function at most once per delay period. 
If the function is called again before the delay has passed, it is ignored. 

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

