

    const wait = (ms) => new Promise((resolve) => setTimeout(resolve, ms));
    
    wait(10 * 1000)
      .then(() => saySomething("10 seconds"))
      .catch(failureCallback);

  
References:
1. https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises#creating_a_promise_around_an_old_callback_api
