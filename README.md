# Introduction to JavaScript and DOM Manipulation

## Objectives

Write basic JavaScript functions.
Manipulate the DOM dynamically.
Respond to user interactions.

## Instructions

- Create a script.js file and link it to a HTML.
- Structure the document using DOCTYPE, html, head, and body.

>[!NOTE]
>  - Write JavaScript that:
>  - Changes text content dynamically.
>  - Modifies CSS styles via JavaScript.
>  - Adds or removes an element when a button is clicked.


# Tasks
- Create a well-structured HTML5 document.
- Use at least 5 different HTML elements.
- Ensure semantic correctness.

-Index. html
- <!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Interactive DOM Example</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>

  <header>
    <h1 id="main-heading">Welcome to My Page</h1>
  </header>

  <section>
    <p id="description">This is a basic example of DOM manipulation using JavaScript.</p>
    <button id="change-text-btn">Change Text</button>
    <button id="toggle-style-btn">Toggle Style</button>
    <button id="add-remove-btn">Add/Remove Element</button>
  </section>

  <footer>
    <p>&copy; 2025 Example Project</p>
  </footer>

  <script src="script.js"></script>
</body>
</html>

script.js

// Change the heading text
document.getElementById("change-text-btn").addEventListener("click", function () {
  document.getElementById("main-heading").textContent = "You've changed the heading!";
});

// Toggle CSS style on the paragraph
document.getElementById("toggle-style-btn").addEventListener("click", function () {
  const description = document.getElementById("description");
  description.style.color = description.style.color === "blue" ? "black" : "blue";
  description.style.fontWeight = description.style.fontWeight === "bold" ? "normal" : "bold";
});

// Add or remove a new element
let isElementAdded = false;

document.getElementById("add-remove-btn").addEventListener("click", function () {
  const section = document.querySelector("section");

  if (!isElementAdded) {
    const newElement = document.createElement("div");
    newElement.id = "dynamic-element";
    newElement.textContent = "I was added dynamically!";
    section.appendChild(newElement);
    isElementAdded = true;
  } else {
    const elementToRemove = document.getElementById("dynamic-element");
    if (elementToRemove) section.removeChild(elementToRemove);
    isElementAdded = false;
  }
});

 styles.css
 
body {
  font-family: Arial, sans-serif;
  margin: 20px;
}

button {
  margin: 10px 5px;
  padding: 8px 12px;
}

#dynamic-element {
  margin-top: 15px;
  color: green;
  font-style: italic;
}

Happy Coding! 💻✨
