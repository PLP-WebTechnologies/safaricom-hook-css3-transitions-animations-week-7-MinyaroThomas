### **Assignment: Building an Interactive and Dynamic Web Page**  

#### **Objective**  
Create a visually engaging and interactive webpage that utilizes **CSS3 transitions and animations**, **advanced JavaScript functions** (including scope, parameters, and return values), and combines **CSS animations with JavaScript** to create dynamic user interactions.  

---

### **Part 1: CSS3 Transitions and Animations**  
1. **Task**:  
   - Use **CSS transitions** to create smooth effects on hover or focus (e.g., buttons that change color or grow).  
   - Use **CSS animations** with `@keyframes` to create dynamic effects like fading, sliding, or rotating.  

2. **Requirements**:  
   - At least **two elements** must include hover or focus transitions.  
   - At least **two animations** must be created using `@keyframes` (e.g., an animated banner or an animated loading spinner).  

---

### **Part 2: JavaScript Functions**  
1. **Task**:  
   - Write JavaScript functions to handle interactivity on the webpage.  
   - Utilize **parameters**, **return values**, and demonstrate an understanding of **scope**.  

2. **Requirements**:  
   - Write at least **three functions**:  
     - A function with parameters and return values (e.g., calculate a value like the area of a rectangle based on user input).  
     - A function that demonstrates the concept of scope (local vs. global variables).  
     - A function to toggle a CSS class that applies an animation (e.g., toggling a "hidden" class for a modal).  

---

### **Part 3: Combining CSS Animations with JavaScript**  
1. **Task**:  
   - Use JavaScript to trigger or control CSS animations dynamically.

***Answers to the quiz: Part 1****
<!DOCTYPE html>
<html>
<head>
<title>CSS Transitions and Animations</title>
<style>
/* CSS Transitions - Button Hover Effect */
.button {
  background-color: #4CAF50; /* Green */
  border: none;
  color: white;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 4px 2px;
  cursor: pointer;
  transition-duration: 0.4s; /* Transition duration for smooth effect */
}

.button:hover {
  background-color: white; /* White on hover */
  color: black;          /* Black text on hover */
  box-shadow: 0 12px 16px 0 rgba(0,0,0,0.24), 0 17px 50px 0 rgba(0,0,0,0.19); /* Shadow on hover */
}

/* CSS Animations - Banner Slide-in */
.banner {
  width: 100%;
  height: 100px;
  background-color: #f0f0f0;
  position: relative;
  animation-name: slideIn;       /* Name of the animation to apply */
  animation-duration: 1s;        /* Duration of the animation */
  animation-timing-function: ease-out; /* Speed curve of the animation */
  animation-fill-mode: forwards;  /* Keep the final state of animation */
  transform: translateX(-100%); /* Start position - off-screen to the left */
}

@keyframes slideIn {
  0% {
    transform: translateX(-100%); /* Start off-screen */
    opacity: 0;                  /* Start invisible */
  }
  100% {
    transform: translateX(0%);    /* End at normal position */
    opacity: 1;                  /* End fully visible */
  }
}
</style>
</head>
<body>

<h2>CSS Transitions Example</h2>
<button class="button">Hover Me for Transition</button>

<hr>

<h2>CSS Animations Example</h2>
<div class="banner">
  <h1>Welcome Banner</h1>
  <p>This banner slides in from the left when the page loads.</p>
</div>

</body>
</html>
            ***** Part 2******
            <!DOCTYPE html>
<html>
<head>
<title>JavaScript Functions Example</title>
<style>
/* Basic Modal Styles (for Toggle Modal example) */
.modal {
  display: none; /* Hidden by default */
  position: fixed; /* Stay in place */
  z-index: 1;    /* Sit on top */
  left: 0;
  top: 0;
  width: 100%;  /* Full width */
  height: 100%; /* Full height */
  overflow: auto; /* Enable scroll if needed */
  background-color: rgba(0,0,0,0.4); /* Black w/ opacity */
}

.modal-content {
  background-color: #fefefe;
  margin: 15% auto; /* 15% from the top and centered */
  padding: 20px;
  border: 1px solid #888;
  width: 80%;      /* Could be more or less, depending on screen size */
}

.close-button {
  color: #aaa;
  float: right;
  font-size: 28px;
  font-weight: bold;
}

.close-button:hover,
.close-button:focus {
  color: black;
  text-decoration: none;
  cursor: pointer;
}
</style>
</head>
<body>

<h2>Vacation Cost Calculator</h2>

<label for="days">Number of days:</label>
<input type="number" id="days" value="7"><br><br>

<label for="dailyRate">Daily rate ($):</label>
<input type="number" id="dailyRate" value="150"><br><br>

<button onclick="calculateCost()">Calculate Total Cost</button>

<p id="costResult"></p>

<hr>

<h2>Modal Toggle Example</h2>
<button onclick="toggleModal()">Open Modal</button>

<div id="myModal" class="modal">
  <div class="modal-content">
    <span class="close-button" onclick="toggleModal()">&times;</span>
    <p>This is a simple Modal.</p>
  </div>
</div>


<script>
// Example 1: Vacation Cost Calculator
function calculateCost() {
  let days = document.getElementById("days").value; // Variable scope: inside calculateCost
  let rate = document.getElementById("dailyRate").value; // Variable scope: inside calculateCost

  let totalCost = calculateTotal(days, rate); // Passing parameters

  document.getElementById("costResult").textContent = "Total cost: $" + totalCost; // Displaying return value
}

function calculateTotal(days, dailyRate) { // Parameters: days, dailyRate
  let daysNum = parseInt(days);
  let rateNum = parseInt(dailyRate);

  if (isNaN(daysNum) || isNaN(rateNum)) {
    return "Invalid input"; // Return value for error case
  }

  return daysNum * rateNum; // Return value: calculated total cost
}


// Example 2: Modal Toggle
function toggleModal() {
  let modal = document.getElementById("myModal"); // Variable scope: inside toggleModal

  if (modal.style.display === "none") {
    modal.style.display = "block"; // Show modal
  } else {
    modal.style.display = "none";  // Hide modal
  }
  // No explicit return value - function implicitly returns 'undefined'
}
</script>

</body>
</html>
************** Part 3 ****************
<!DOCTYPE html>
<html>
<head>
<title>Combining CSS Animation and JavaScript</title>
<style>
/* Modal Styles with Fade-in Animation */
.modal {
  display: none; /* Hidden by default */
  position: fixed; /* Stay in place */
  z-index: 1;    /* Sit on top */
  left: 0;
  top: 0;
  width: 100%;  /* Full width */
  height: 100%; /* Full height */
  overflow: auto; /* Enable scroll if needed */
  background-color: rgba(0,0,0,0.4); /* Black w/ opacity */
  animation-duration: 0.5s; /* Animation duration for fade-in */
  animation-timing-function: ease-out;
  animation-fill-mode: forwards;
}

.modal-content {
  background-color: #fefefe;
  margin: 15% auto; /* 15% from the top and centered */
  padding: 20px;
  border: 1px solid #888;
  width: 80%;      /* Could be more or less, depending on screen size */
}

.close-button {
  color: #aaa;
  float: right;
  font-size: 28px;
  font-weight: bold;
}

.close-button:hover,
.close-button:focus {
  color: black;
  text-decoration: none;
  cursor: pointer;
}

/* Fade-in animation definition */
@keyframes fadeIn {
  from {opacity: 0;} /* Start fully transparent */
  to {opacity: 1;}   /* End fully opaque */
}

/* Class to trigger the fade-in animation */
.modal.fade-in {
  display: block !important; /* Override display: none; to show modal */
  animation-name: fadeIn;    /* Apply the fadeIn animation */
}
</style>
</head>
<body>

<h2>Combining CSS Animation and JavaScript</h2>
<button onclick="openModal()">Open Modal with Fade-in</button>

<div id="myAnimatedModal" class="modal">
  <div class="modal-content">
    <span class="close-button" onclick="closeModal()">&times;</span>
    <p>Modal with a Fade-in Animation triggered by JavaScript.</p>
  </div>
</div>

<script>
function openModal() {
  let modal = document.getElementById("myAnimatedModal");
  modal.classList.add("fade-in"); // JavaScript adds the class to trigger CSS animation
}

function closeModal() {
  let modal = document.getElementById("myAnimatedModal");
  modal.classList.remove("fade-in"); // JavaScript removes the class to hide (and reset)
  // Optional: Reset display to none after animation for proper initial state
  setTimeout(() => { modal.style.display = "none"; }, 500); // Wait for animation duration
}
</script>

</body>
</html>

2. **Requirements**:  
   - Create an interactive element (e.g., a button, card, or slider) that triggers an animation when clicked.  
   - Dynamically add or remove CSS classes to control the animation.  
   - Ensure that the animation resets properly when triggered multiple times.  

---
