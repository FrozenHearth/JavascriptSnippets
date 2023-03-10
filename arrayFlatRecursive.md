Recursive approach to flatten an array without using array.flat() method.

    function flatten(arr) {
      let result = [];
      for (let i = 0; i < arr.length; i++) {
        if (Array.isArray(arr[i])) {
          result = [...result, ...flatten(arr[i])];
        } else {
          result.push(arr[i]);
        }
      }
      return result;
    }
