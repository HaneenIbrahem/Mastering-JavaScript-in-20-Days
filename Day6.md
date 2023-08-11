# Day 1: JavaScript: From First Steps to Professional
This README file summarizes the JavaScript lesson on Data Fetching & Promises, Destructuring Data, Async, Modules and Wrapping up.

## Lesson Summary

fetch(): lets us use JS to load data from APIs

Promises: can be in 3 possible states:
- pending: still waiting for the value, hang tight.
- fulfilled: (aka: "resolved"): finally got the valye, all done.
- rejected: sorry couldn't get the value, all done. it likes time for Promises to resolve, so they are "asynchronous"

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

**index.html:**
```html
<!DOCTYPE html>
<html>
<head>
  <title>Rick & Morty Character List</title>
  <link rel="stylesheet" href="./style.css">
</head>
<body>
  <h1 class="title">Rick & Morty Character List!</h1>
  <ul id="characterList"></ul>

  <script src="./script.js"></script>
</body>
</html>
```

**style.css:**
```css
/* Add this CSS to your styles.css file */

.character-list {
    list-style: none;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 20px;
    padding: 0;
  }
  
  .character {
    border: 1px solid #ccc;
    padding: 10px;
    text-align: center;
    width: 200px;
  }
  
  .character img {
    max-width: 100%;
    height: auto;
  }
  
  .character h2 {
    margin-top: 10px;
    font-size: 18px;
  }
  
  .character p {
    margin: 5px 0;
    font-size: 14px;
  }
```

**script.js:**
```javascript
// Step 1: Use the Fetch API to retrieve character data
async function fetchCharacterData() {
    try {
      const response = await fetch('https://rickandmortyapi.com/api/character?status=alive');
      if (!response.ok) {
        throw new Error('Network response was not ok');
      }
      const data = await response.json();
      return data;
    } catch (error) {
      console.error('Error fetching character data:', error);
      const errorMessage = document.createElement('p');
      errorMessage.textContent = 'An error occurred while fetching character data.';
      document.getElementById('characterList').appendChild(errorMessage);
      return null;
    }
  }
  
  // Step 2-7: Handle potential errors, filter characters, display the list
  fetchCharacterData().then(data => {
    if (data) {
      const aliveCharacters = data.results;
      const charactersToDisplay = aliveCharacters.slice(0, 50);
      const characterList = document.getElementById('characterList');
  
      charactersToDisplay.forEach(character => {
        const li = document.createElement('li');
        li.classList.add('character-item'); // Add a class for styling
        
        const img = document.createElement('img');
        img.src = character.image;
        img.alt = `${character.name} image`;
        li.appendChild(img);
        
        const info = document.createElement('div');
        info.classList.add('character-info'); // Add a class for styling
        info.innerHTML = `
          <h2>${character.name}</h2>
          <p>Location: ${character.location.name}</p>
          <p>Species: ${character.species}</p>
          <p>Gender: ${character.gender}</p>
        `;
        li.appendChild(info);
        
        characterList.appendChild(li);
      });
    }
  });
```

![Result](imgs/Screenshot%202023-08-11%20235108.png)

![Result](imgs/Screenshot%2023-08-11%235156.png)
