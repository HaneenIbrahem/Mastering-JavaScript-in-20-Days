# Day 1: JavaScript: From First Steps to Professional
This README file summarizes the JavaScript lesson on Data Fetching & Promises, Destructuring Data, Async, Modules and Wrapping up.

## Lesson Summary

fetch(): lets us use JS to load data from APIs

Promises: can be in 3 possible states:
- 
-
-

await : let us tell JS to stop and wait for an asynchronous operation tp finish

response.json(): parse the body ad JSON object, it gives us another promisee

We can use `...` to collect remaining values 

## Exercise 1: TODO 2

  ```javascript
  function getBreedFromURL(url) {
        let unsplitBreed = url.split("/")[4];
        let [breed, subbreed] = unsplitBreed.split("-");
        return [subbreed, breed].join(" ").trim;
    } 
  ```

## Exercise 2: TODO 3 + 4

 ```javascript
  async function fetchMessage(url) {
        const response = await fetch(url);
        const body = await response.json();
        const {message} = body;
        return message;   
    }
function renderButtons(choicesArray, correctAnswer) {

        // Event handler function to compare the clicked button's value to correctAnswer
        // and add "correct"/"incorrect" classes to the buttons as appropriate
        function buttonHandler(e) {
            if (e.target.value === correctAnswer) {
                e.target.classList.add("correct");
            } else {
                e.target.classList.add("incorrect");
                document.querySelector(`button[value="${correctAnswer}"]`).classList.add("correct");
            }
        }

        const options = document.getElementById("options"); // Container for the multiple-choice buttons

        // TODO 4
        // For each of the choices in choicesArray,
        // Create a button element whose name, value, and textContent properties are the value of that choice,
        // attach a "click" event listener with the buttonHandler function,
        // and append the button as a child of the options element
        for(let choice of choicesArray){
            const button = document.createElement("button");
            button.textContent = choice;
            button.value = choice;
            button.name = choice;
            button.addEventListener("click", buttonHandler);
            options.appendChild(button);
        }
    }
function renderQuiz(imgUrl, correctAnswer, choices) {
        const image = document.createElement("img");
        image.setAttribute("src", imgUrl);
        const frame = document.getElementById("image-frame");

        image.addEventListener("load", () => {
            // Wait until the image has finished loading before trying to add elements to the page
            frame.replaceChildren(image);
            renderButtons(choices, correctAnswer);
        })
        
    }

    // Function to load the data needed to display the quiz
    async function loadQuizData() {
        document.getElementById("image-frame").textContent = "Fetching doggo...";
        
        const doggoImgUrl = await fetchMessage(RANDOM_IMG_ENDPOINT);
        const correctBreed = getBreedFromURL(doggoImgUrl);
        const breedChoices = getMultipleChoices(3, correctBreed, BREEDS);

        return [doggoImgUrl, correctBreed, breedChoices];
    }
  ```
## Exercise 2: TODO 5
```javascript
   const [imgUrl, correctAnswer, choices] = await loadQuizData();
    renderQuiz(imgUrl, correctAnswer, choices); 
```


## DELIEVERABLES:
