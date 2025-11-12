# Ex04 Simple Calculator - React Project
## Date:13.10.2025

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
```
## app.js

import { useState } from "react";
import "./App.css";

function App() {
  const [input, setInput] = useState("0");
  const [lastResult, setLastResult] = useState("");

  const handleClick = (value) => {
    setInput((prev) => (prev === "0" ? value : prev + value));
  };

  const handleClear = () => {
    setInput("0");
    setLastResult("");
  };

  const handleBackspace = () => {
    setInput((prev) => (prev.length > 1 ? prev.slice(0, -1) : "0"));
  };

  const handleCalculate = () => {
    try {
      const result = eval(input).toString();
      setLastResult(input + " = " + result);
      setInput(result);
    } catch {
      setInput("Error");
    }
  };

  return (
    <div className="app-container">
      <div className="calculator-container">
        <div className="calculator">
          <div className="last-result">{lastResult}</div>
          <div className="display">{input}</div>
          <div className="buttons">
            <button className="button number" onClick={() => handleClick("7")}>7</button>
            <button className="button number" onClick={() => handleClick("8")}>8</button>
            <button className="button number" onClick={() => handleClick("9")}>9</button>
            <button className="button operator" onClick={() => handleClick("/")}>÷</button>
            <button className="button number" onClick={() => handleClick("4")}>4</button>
            <button className="button number" onClick={() => handleClick("5")}>5</button>
            <button className="button number" onClick={() => handleClick("6")}>6</button>
            <button className="button operator" onClick={() => handleClick("*")}>×</button>
            <button className="button number" onClick={() => handleClick("1")}>1</button>
            <button className="button number" onClick={() => handleClick("2")}>2</button>
            <button className="button number" onClick={() => handleClick("3")}>3</button>
            <button className="button operator" onClick={() => handleClick("-")}>−</button>
            <button className="button number" onClick={() => handleClick("00")}>00</button>
            <button className="button number" onClick={() => handleClick("0")}>0</button>
            <button className="button number" onClick={() => handleClick(".")}>.</button>
            <button className="button operator" onClick={() => handleClick("+")}>+</button>
            <button className="button backspace" onClick={handleBackspace}>⌫</button>
            <button className="button equals" onClick={handleCalculate}>=</button>
            <button className="button clear" onClick={handleClear}>Clear</button>
          </div>
        </div>
      </div>
      
      {/* Footer is outside the calculator box */}
      <footer className="footer">
        &copy; 2025 Janarthanan K 212223040072. All Rights Reserved.
      </footer>
    </div>
  );
}

export default App;

```
## APP.CSS

```
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: Arial, sans-serif;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background: linear-gradient(135deg, #3498db, #8e44ad);
}

.container {
  width: 300px;
}

.calculator {
  background-color: white;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
}

.display input {
  width: 100%;
  height: 60px;
  font-size: 24px;
  text-align: right;
  margin-bottom: 10px;
  padding: 5px;
  border: none;
  border-radius: 5px;
  background-color: rgb(240, 240, 240);
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
}

button {
  height: 60px;
  font-size: 20px;
  background-color: rgb(91, 91, 151);
  color: white;
  border: none;
  border-radius: 10px;
  cursor: pointer;
}

button:hover {
  background-color: rgb(137, 22, 245);
}

button:active {
  background-color: rgb(100, 100, 200);
}

button:nth-child(16) {
  background-color: rgb(220, 53, 69); /* Red for 'C' */
}


```



## OUTPUT

<img width="538" height="558" alt="image" src="https://github.com/user-attachments/assets/c36ccdc4-8694-4ab5-bca1-623af9d85816" />

## RESULT
The program for developing a simple calculator in React.js is executed successfully.
