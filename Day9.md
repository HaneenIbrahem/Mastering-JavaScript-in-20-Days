# Day 9: JavaScript: The Hard Parts, v2
This README file summarizes the JavaScript lesson on Promises.

## Lesson Summary

Initiate background web browser work **and** Return a placeholder object (promise) immediately in JavaScript

▶️ Promise object: it is just an object automatically created in JaveScript by fetch().

▶️ Any code we want to run on the returned data must also be saved on the promise object

Added using **.then** method to the hidden property 'onFulfilment'.

Promise objects will automatically trigger the attached function to run (with its input being the returned data 

------
**Problems**
- 99% of developers have no idea how they’re working under the hood
- Debugging becomes super-hard as a result
- Developers fail technical interviews
**Benefits**
- Cleaner readable style with pseudo-synchronous style code
- Nice error handling process

Example:
```javaScript
function display(data {console.log(data)}
function printHello(){console.log("Hello");}
function blockFor300ms(){/* blocks js thread for 300ms */}
setTimeout(printHello, 0);
const futureData = fetch('https://twitter.com/will/tweets/1')
futureData.then(display)
blockFor300ms()
console.log("Me first!");


/*
console:
Me first
hi
Hello
*/
```
**We have rules for the execution of our asynchronously delayed code**

- Hold promise-deferred functions in a microtask queue and callback function in a task queue (Callback queue) when the Web Browser Feature (API) finishes
- Add the function to the Call stack (i.e. run the function) when: 

 Call stack is empty & all global code run (Have the Event Loop check this condition).
- Prioritize functions in the microtask queue over the Callback queue

**Non-blocking applications:** This means we don’t have to wait in the single thread and don't block further code from running

**However long it takes:** We cannot predict when our Browser feature’s work will finish so we let JS handle automatically running the function on its completion.

**Web applications:** Asynchronous JavaScript is the backbone of the modern web - letting us build fast 'non-blocking' applications

## DELIEVERABLES:

[Question 1:](https://github.com/orjwan-alrajaby/gsg-QA-Nablus-training-2023/blob/main/learning-sprint-1/week2%20-%20javaScript-the-hard-parts-v2/day%203/tasks.md#question-1)
```JavaScript

const task1 = (cb) => setTimeout(() => {
    const message = "Task 1 has executed successfully!";
    cb(message);
  }, 3000)
  
  const task2 = (cb) => setTimeout(() => {
    const message = "Task 2 has executed successfully!";
    cb(message);
  }, 0)
  
  const task3 = (cb) => setTimeout(() => {
    const message = "Task 3 has executed successfully!";
    cb(message);
  }, 1000)
  
  const task4 = (cb) => setTimeout(() => {
    const message = "Task 4 has executed successfully!";
    cb(message);
  }, 2000)
  
  const task5 = (cb) => setTimeout(() => {
    const message = "Task 5 has executed successfully!";
    cb(message);
  }, 4000)
  
  const asyncTasks = [task1, task2, task3, task4, task5];
  
  const executeInSequenceWithCBs = (tasks, callback) => {
    const messages = []; // Array to store messages from tasks
  
    // Recursive function to run tasks in sequence
    const runTasks = (index) => {
      if (index >= tasks.length) {
        callback(messages);
        return;
      }
  
      const currentTask = tasks[index];
      currentTask((message) => {
        messages.push(message); // Collect the message from the task
        runTasks(index + 1);    // Move to the next task
      });
    };
  
    // Start running tasks from index 0
    runTasks(0);
  };
  
  // Usage example:
  executeInSequenceWithCBs(asyncTasks, (messages) => {
    console.log(messages); // Output: ["Task 1 has executed successfully!", "Task 2 has executed successfully!", ...]
  });
  
```

[Question 2:](https://github.com/orjwan-alrajaby/gsg-QA-Nablus-training-2023/blob/main/learning-sprint-1/week2%20-%20javaScript-the-hard-parts-v2/day%203/tasks.md#question-2)
```JavaScript
const apis = [
  {
    apiName: "products", 
    apiUrl: "https://dummyjson.com/products",
  }, 
  {
    apiName: "users", 
    apiUrl: "https://dummyjson.com/users",
  }, 
  {
    apiName: "posts", 
    apiUrl: "https://dummyjson.com/posts",
  }, 
  {
    apiName: "comments", 
    apiUrl: "https://dummyjson.com/comments",
  }
];

const executeInParallelWithPromises = (apis) => {
  // Create an array of promises for fetching data from each API
  const promises = apis.map(api => {
    return fetch(api.apiUrl) // Fetch data from the API URL
      .then(response => response.json()) // Parse JSON response
      .then(apiData => ({
        apiName: api.apiName,
        apiUrl: api.apiUrl,
        apiData: apiData
      }));
  });

  // Use Promise.all() to wait for all promises to resolve
  return Promise.all(promises);
};

// Execute the APIs in parallel
executeInParallelWithPromises(apis)
  .then(results => {
    console.log(results); // Array of results for each API
  })
  .catch(error => {
    console.error("Error:", error);
  });

```

[Question 3:](https://github.com/orjwan-alrajaby/gsg-QA-Nablus-training-2023/blob/main/learning-sprint-1/week2%20-%20javaScript-the-hard-parts-v2/day%203/tasks.md#question-3)
```JavaScript
const apis = [
  {
    apiName: "products", 
    apiUrl: "https://dummyjson.com/products",
  }, 
  {
    apiName: "users", 
    apiUrl: "https://dummyjson.com/users",
  }, 
  {
    apiName: "posts", 
    apiUrl: "https://dummyjson.com/posts",
  }, 
  {
    apiName: "comments", 
    apiUrl: "https://dummyjson.com/comments",
  }
];

const executeInSequenceWithPromises = async (apis) => {
  const results = [];

  for (const api of apis) {
    try {
      const response = await fetch(api.apiUrl);
      const apiData = await response.json();

      results.push({
        apiName: api.apiName,
        apiUrl: api.apiUrl,
        apiData: apiData
      });
    } catch (error) {
      console.error(`Error fetching data for ${api.apiName}:`, error);
    }
  }

  return results;
};

// Execute the APIs sequentially
executeInSequenceWithPromises(apis)
  .then(results => {
    console.log(results); // Array of results for each API
  })
  .catch(error => {
    console.error("Error:", error);
  });

```

