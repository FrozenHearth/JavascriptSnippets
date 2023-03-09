Recursive approach to flatten an array without using array.flat() method.

    const flatten = function(arr, result = []) {
      for (let i = 0, i < arr.length; i++) {
        if (Array.isArray(value)) {
          flatten(arr[i], result);
        } else {
          result.push(arr[i]);
        }
      }
      return result;
    };
