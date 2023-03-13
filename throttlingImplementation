In this implementation, the throttle function takes a function to be throttled and a delay time in milliseconds. 
It returns a new function that will execute the original function at most once per delay period. 
If the function is called again before the delay has passed, it is ignored. 

      function throttle(func, delay) {
      let lastTime = 0;
      return function() {
        const currentTime = new Date().getTime();
        if (currentTime - lastTime > delay) {
          lastTime = currentTime;
          func(...arguments);
        }
      };
    }

