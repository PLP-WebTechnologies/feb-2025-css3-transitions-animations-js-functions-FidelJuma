# CSS3 Transitions, Animations, and Advanced JavaScript Functions

## Objectives

Create smooth CSS transitions and animations.
Use JavaScript functions for dynamic behavior.
Implement local storage for data persistence.

## Instructions
Add CSS animations to elements like buttons or images.

>[!NOTE]
> - Write a JavaScript function that:
> - Stores and retrieves user preferences using localStorage.
> - Implements an animation triggered by user actions.

## Tasks

Create a CSS animation.
Store data in localStorage.
Apply JavaScript to trigger animations.
Sure! Here's how you can create a CSS animation, store data in `localStorage`, and use JavaScript to trigger the animation:

### 1. **CSS Animation**
We'll create a simple CSS animation that changes the background color of an element when triggered.

```css
/* CSS Animation */
@keyframes colorChange {
  0% {
    background-color: red;
  }
  100% {
    background-color: blue;
  }
}

#myElement {
  width: 200px;
  height: 200px;
  background-color: red;
  transition: background-color 0.5s ease;
}

/* Class to apply animation */
.animate {
  animation: colorChange 2s forwards;
}
```

### 2. **HTML Structure**
We'll create a simple button to trigger the animation and a `div` element that will be animated.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CSS Animation with JavaScript</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>

  <div id="myElement"></div>
  <button id="triggerAnimation">Trigger Animation</button>

  <script src="script.js"></script>
</body>
</html>
```

### 3. **JavaScript to Trigger Animation and Store Data in `localStorage`**
Now, we will use JavaScript to trigger the animation when the button is clicked and store some data in `localStorage`.

```javascript
// script.js

document.getElementById("triggerAnimation").addEventListener("click", function() {
  // Apply the animation class
  const element = document.getElementById("myElement");
  element.classList.add("animate");

  // Store some data in localStorage (for example, "animationTriggered" as true)
  localStorage.setItem("animationTriggered", "true");

  // Check if the animation was triggered previously
  const animationStatus = localStorage.getItem("animationTriggered");
  if (animationStatus) {
    console.log("Animation was triggered before!");
  }
});
```

### Explanation:
1. **CSS Animation (`@keyframes colorChange`)**: This animation smoothly transitions the background color from red to blue.
2. **JavaScript (`localStorage`)**: When the button is clicked, it:
   - Adds the `animate` class to the `#myElement`, which triggers the animation.
   - Stores a key-value pair in `localStorage` to keep track of whether the animation was triggered before (`localStorage.setItem`).
   - Logs a message in the console to indicate whether the animation was previously triggered (`localStorage.getItem`).

### How It Works:
1. When you click the "Trigger Animation" button, the background color of the `#myElement` changes from red to blue with a smooth transition, thanks to the `colorChange` animation.
2. The data `"animationTriggered"` is stored in `localStorage`, which can be used to check if the animation has been triggered before, even after the page is reloaded.

### Summary:
- **CSS**: Defines the animation using `@keyframes` and the `.animate` class.
- **JavaScript**: Triggers the animation and stores data in `localStorage` to keep track of whether the animation has been triggered before.
Happy Coding! 💻✨
