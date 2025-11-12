# Ex04 Simple Calculator - React Project
## Date:11.04.2025

## AIM
To  develop a Simple Calculator using React.js with clean and responsive design, ensuring a smooth user experience across different screen sizes.

## ALGORITHM
### STEP 1
Create a React App.

### STEP 2
Open a terminal and run:
  <ul><li>npx create-react-app simple-calculator</li>
  <li>cd simple-calculator</li>
  <li>npm start</li></ul>

### STEP 3
Inside the src/ folder, create a new file Calculator.js and define the basic structure.

### STEP 4
Plan the UI: Display screen, number buttons (0-9), operators (+, -, *, /), clear (C), and equal (=).

### STEP 5
Create a new file Calculator.css in src/ and add the styling.

### STEP 6
Open src/App.js and modify it.

### STEP 7
Start the development server.
  npm start

### STEP 8
Open http://localhost:3000/ in the browser.

### STEP 9
Test the calculator by entering numbers and operations.

### STEP 10
Fix styling issues and refine content placement.

### STEP 11
Deploy the website.

### STEP 12
Upload to GitHub Pages for free hosting.

## PROGRAM
## calculator.css
```css
.calculator {
  width: 300px;
  margin: 50px auto;
  padding: 20px;
  border-radius: 10px;
  background-color: #222;
  text-align: center;
}

.display {
  width: 100%;
  height: 50px;
  font-size: 1.5em;
  text-align: right;
  margin-bottom: 10px;
  padding: 5px;
  border-radius: 5px;
  border: none;
  background-color: #333;
  color: white;
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
}

button {
  padding: 15px;
  font-size: 1.2em;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  background-color: #444;
  color: white;
  transition: 0.3s;
}

button:hover {
  background-color: #666;
}

.clear {
  grid-column: span 4;
  background-color: red;
}

.clear:hover {
  background-color: darkred;
}
.App {
  display: flex;
  flex-direction: column;
  align-items: center;
  min-height: 100vh; 
  justify-content: center;
  background-color: #121212;
  color: white;
}
footer {
  margin-top: 20px;
  padding: 10px;
  font-size: 1rem;
  color: #bbb;
  position: absolute;
  bottom: 10px;
  width: 100%;
  text-align: center;
}
```
## calculator.js
```js
import React, { useState } from "react";
import "./Calculator.css";

const Calculator = () => {
  const [input, setInput] = useState("");

  const handleClick = (value) => {
    setInput((prev) => prev + value);
  };

  const handleClear = () => {
    setInput("");
  };

  const handleCalculate = () => {
    try {
      setInput(eval(input).toString()); // Evaluate the input expression
    } catch (error) {
      setInput("Error");
    }
  };

  return (
    <div className="calculator">
      <input type="text" value={input} readOnly className="display" />
      <div className="buttons">
        {["7", "8", "9", "/", "4", "5", "6", "*", "1", "2", "3", "-", "0", ".", "=", "+"].map((char) => (
          <button key={char} onClick={() => (char === "=" ? handleCalculate() : handleClick(char))}>
            {char}
          </button>
        ))}
        <button className="clear" onClick={handleClear}>
          C
        </button>
      </div>
    </div>
  );
};

export default Calculator;
```
## APP.JS
```js
import React from "react";
import Calculator from "./components/Calculator";

function App() {
  return (
    <div className="App">
      <h1 style={{ textAlign: "center", color: "#fff" }}>Simple Calculator</h1>
      <Calculator />
    </div>
  );
}

export default App;
```
## OUTPUT:
![Screenshot 2025-05-06 104416 (6)](https://github.com/user-attachments/assets/b23c2aff-b5b0-4ccc-bef9-813bb2b443b6)

![Screenshot 2025-05-06 104428](https://github.com/user-attachments/assets/78892c7e-423a-4792-8f05-082ddec5f373)



## RESULT
The program for developing a simple calculator in React.js is executed successfully.
