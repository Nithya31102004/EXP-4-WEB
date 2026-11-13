# EXPERIMENT 4: REACT LAB EXERCISE – EVENT HANDLING IN REACT

**Name:** NITHYA T  
**Register Number:** 2305001023
**Department:** CSE

## 1. AIM

To understand and implement event handling in React using events such as onClick, onChange, and onSubmit.

## 2. ALGORITHM

1. Start the program.
2. Create a React project using Vite and open it in VS Code.
3. Import useState from React in App.jsx.
4. Create a counter and use onClick events to increase and decrease the count.
5. Create a Show/Hide section and use onClick to display or hide a message.
6. Create a student form with Name, Register Number, and Department fields.
7. Use onChange events to update the form values while typing.
8. Use onSubmit to display the entered student details.
9. Add CSS to display each exercise in a separate card.
10. Run the application using npm run dev.
11. Verify that the counter, show/hide message, and student form work correctly.
12. Stop the program.

## 3. PROJECT STRUCTURE

```text
Experiment_04/
├── index.html
├── package.json
└── src/
    ├── main.jsx
    ├── App.jsx
    ├── App.css
    └── index.css
```

## 4. PROGRAMS

### Program 1: App.jsx

**Location:** `src/App.jsx`

```jsx
import { useState } from "react"
import "./App.css"

function App() {
  const [count, setCount] = useState(0)
  const [showMessage, setShowMessage] = useState(false)
  const [name, setName] = useState("")
  const [registerNo, setRegisterNo] = useState("")
  const [department, setDepartment] = useState("")
  const [submitted, setSubmitted] = useState(false)

  function handleSubmit(event) {
    event.preventDefault()
    setSubmitted(true)
  }

  return (
    <div className="container">
      <h1>React Event Handling Exercise</h1>

      <div className="card">
        <h2>Counter</h2>
        <p>Count: {count}</p>
        <button onClick={() => setCount(count + 1)}>+</button>
        <button onClick={() => setCount(count - 1)}>-</button>
      </div>

      <div className="card">
        <h2>Show / Hide</h2>
        <button onClick={() => setShowMessage(!showMessage)}>
          {showMessage ? "Hide Message" : "Show Message"}
        </button>
        {showMessage && <p className="message">Welcome to React!</p>}
      </div>

      <div className="card">
        <h2>Student Form</h2>

        <form onSubmit={handleSubmit}>
          <input
            type="text"
            placeholder="Enter Name"
            value={name}
            onChange={(event) => setName(event.target.value)}
            required
          />

          <input
            type="text"
            placeholder="Enter Register Number"
            value={registerNo}
            onChange={(event) => setRegisterNo(event.target.value)}
            required
          />

          <input
            type="text"
            placeholder="Enter Department"
            value={department}
            onChange={(event) => setDepartment(event.target.value)}
            required
          />

          <button type="submit">Submit</button>
        </form>

        {submitted && (
          <div className="details">
            <h3>Student Details</h3>
            <p>Name: {name}</p>
            <p>Register No: {registerNo}</p>
            <p>Department: {department}</p>
          </div>
        )}
      </div>
    </div>
  )
}

export default App
```

### Program 2: App.css

**Location:** `src/App.css`

```css
body {
  margin: 0;
  font-family: Arial, Helvetica, sans-serif;
  background: #f4f7fb;
  color: #222;
}

.container {
  min-height: 100vh;
  text-align: center;
  padding: 40px 20px;
}

.container h1 {
  color: #1e3a5f;
  margin-bottom: 30px;
}

.card {
  width: 380px;
  margin: 20px auto;
  padding: 24px;
  background: white;
  border: 1px solid #dfe5ec;
  border-radius: 12px;
  box-shadow: 0 6px 18px rgba(0, 0, 0, 0.08);
}

.card h2 {
  color: #2563eb;
  border-bottom: 2px solid #e5e7eb;
  padding-bottom: 10px;
}

.card p {
  font-size: 17px;
}

button {
  padding: 10px 18px;
  margin: 6px;
  border: none;
  border-radius: 6px;
  background: #2563eb;
  color: white;
  font-size: 15px;
  cursor: pointer;
}

button:hover {
  background: #1d4ed8;
}

input {
  width: 90%;
  padding: 10px;
  margin: 8px 0;
  border: 1px solid #cbd5e1;
  border-radius: 6px;
  font-size: 15px;
}

.message {
  margin-top: 18px;
  font-weight: bold;
  color: #16a34a;
}

.details {
  margin-top: 20px;
  padding: 15px;
  background: #f8fafc;
  border-radius: 8px;
  text-align: left;
}

.details h3 {
  color: #2563eb;
  text-align: center;
}
```

### Program 3: main.jsx

**Location:** `src/main.jsx`

```jsx
import React from 'react'
import ReactDOM from 'react-dom/client'
import App from './App.jsx'
import './index.css'

ReactDOM.createRoot(document.getElementById('root')).render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
)
```

### Program 4: index.css

**Location:** `src/index.css`

```css
* {
  box-sizing: border-box;
}

html, body {
  margin: 0;
  min-width: 320px;
  min-height: 100%;
}
```

## 5. EXECUTION

1. Open the Experiment_04 folder in VS Code.
2. Open the terminal.
3. Install the dependencies:

```bash
npm install
```

4. Run the React application:

```bash
npm run dev
```

5. Open the localhost URL displayed in the terminal.
6. Test the counter, Show/Hide button, and student registration form.

## 6. BUILD CHECK

```bash
npm run build
```

## 7. OUTPUT

<img width="804" height="462" alt="image" src="https://github.com/user-attachments/assets/6e1ad2bd-894e-4bfe-b0e7-dcd63c8248cf" />


## 8. OBSERVATION

The application successfully handles button click, input change, and form submission events. The counter updates, the message can be shown or hidden, and the entered student details are displayed after form submission.

## 9. RESULT

Thus, event handling in React was implemented successfully using onClick, onChange, and onSubmit events.
