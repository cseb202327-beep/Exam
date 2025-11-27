# Exam
Enjoy the exam by copy pasting the code 
**1B**
<!DOCTYPE html>
<html>
<head>
       <meta charset="UTF-8">
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Element Selectors Demo</title>
  <style>	
    body {
      font-family: Arial, sans-serif;
      background-color: #eef2f7;
      padding: 20px;
      color: #333;
    }
    h1 {
      color: #2c3e50;
      text-align: center;
      background-color: #dfe6e9;
      padding: 15px;
      border-radius: 8px;
    }
    p.info {
      background-color: #fff;
      padding: 8px 12px;
      margin: 10px 0;
      border-left: 5px solid #3498db;
      border-radius: 5px;
    }
    ul {
      background-color: #fff;
      padding: 15px;
      border-radius: 8px;
      list-style-type: square;
      border: 1px solid #ccc;
    }
    ul li {
      margin: 5px 0;
      padding: 5px;
      transition: background 0.3s;
    }
    ul li:hover {
      background-color: #f1c40f;
      color: white;
      cursor: pointer;
    }
    .result {
      margin-top: 20px;
      padding: 15px;
      border: 2px solid #2980b9;
      background-color: #ecf0f1;
      border-radius: 8px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
      font-size: 16px;
    }
    strong {
      color: #2980b9;
    }
  </style></head>
<body>
  <h1 id="mainHeading">Welcome to Selector Demo</h1>
  <p class="info">This is a paragraph with class "info".</p>
  <p class="info">This is another paragraph with class "info".</p>

  <ul>
    <li>Item One</li>
    <li>Item Two</li>
  </ul>
  <div id="output" class="result"></div>
  <script>
    let heading = document.getElementById("mainHeading");
    let infoParagraphs = document.getElementsByClassName("info");
    let listItems = document.getElementsByTagName("li");
    let firstInfo = document.querySelector(".info");
    let allInfo = document.querySelectorAll(".info");
    let output = document.getElementById("output");
    output.innerHTML = `
      <strong>Selected Elements:</strong><br><br>
      Heading text (by ID): ${heading.textContent} <br>
      First paragraph (by class): ${infoParagraphs[0].textContent} <br>
      Number of paragraphs with class 'info': ${infoParagraphs.length} <br>
      First list item (by tag): ${listItems[0].textContent} <br>
      Using querySelector (first .info): ${firstInfo.textContent} <br>
      Total elements with .info using querySelectorAll: ${allInfo.length}
    `;
  </script>
</body>
</html>
**1C**
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Multiple Event Listeners</title>
<style>
  body {
    font-family: Arial, sans-serif;
    background-color: #eef2f7;
    padding: 20px;
    text-align: center;
  }
  h2 {
    color: #2c3e50;
    margin-bottom: 20px;
  }
  button, input {
    margin: 10px 0;
    padding: 10px 15px;
    font-size: 16px;
    border: none;
    border-radius: 5px;
    transition: background 0.3s;
  }
  button {
    background-color: #3498db;
    color: white;
  }
  button:hover {
    background-color: #2980b9;
    cursor: pointer;
  }
  #hoverBox {
    width: 200px;
    height: 60px;
    background-color: lightblue;
    text-align: center;
    line-height: 60px;
    margin: 15px auto;
    border-radius: 8px;
    font-weight: bold;
    transition: transform 0.3s, background 0.3s;
  }
  #hoverBox:hover {
    transform: scale(1.05);
    background-color: #5dade2;
    color: white;
  }
  #output {
    margin-top: 20px;
    font-size: 18px;
    color: darkblue;
    background: #d6eaf8;
    padding: 10px;
    border-radius: 5px;
    border: 1px solid #aed6f1;
    width: 60%;
    margin-inline: auto;
  }
</style>
</head>
<body>
  <h2>JavaScript Event Listeners Demo</h2>
  <button id="clickBtn">Click Me</button><br>
  <button id="dblClickBtn">Double Click Me</button><br>

  <div id="hoverBox">Hover over me</div><br>
  <input type="text" id="textInput" placeholder="Type something here"><br>
  <p id="output">Event messages will appear here.</p>
  <script>
    const $ = id => document.getElementById(id);
    const output = $("output");
    const setText = msg => output.innerText = msg;
    const events = [
      { el: $("clickBtn"), type: "click", msg: "Button clicked!" },
      { el: $("clickBtn"), type: "mouseenter", msg: "Mouse is over the Click button!" },
      { el: $("clickBtn"), type: "mouseleave", msg: "Mouse left the Click button!" },
      { el: $("dblClickBtn"), type: "dblclick", msg: "Button double-clicked!" },
      { el: $("hoverBox"), type: "mouseover", msg: "Mouse is over the box!" },
      { el: $("hoverBox"), type: "mouseout", msg: "Mouse left the box!" },
      { el: $("hoverBox"), type: "wheel", msg: "Mouse wheel used over the box!" },
      { el: $("textInput"), type: "focus", msg: "Input box focused!" },
      { el: $("textInput"), type: "blur", msg: "Input box lost focus!" },
    ];
    events.forEach(({ el, type, msg }) => el.addEventListener(type, () => setText(msg)));
    const textInput = $("textInput");
    textInput.addEventListener("keydown", e => setText(`Key pressed: ${e.key}`));
    textInput.addEventListener("keyup", () => setText(`You typed: ${textInput.value}`));
  </script>
</body>
</html>
**1E**
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Three Types of Functions Demo</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 2rem;
      background-color: #fafafa;
    }
    h2 {
      text-align: center;
      color: #333;
    }
    #output {
      margin-top: 20px;
      padding: 15px;
      border-radius: 8px;
      background: #ffffff;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
      line-height: 1.6;
    }
    strong {
      color: #007acc;
    }
    code {
      background: #f4f4f4;
      padding: 2px 6px;
      border-radius: 4px;
      font-family: Consolas, monospace;
      color: #c7254e;
    }
  </style>
</head>
<body>
  <h2>JavaScript Function Types Demo</h2>
  <div id="output"></div>
  <script>
    function add(a, b) {
      return a + b;
    }
    const multiply = function (a, b) {
      return a * b;
    };
    const divide = (a, b) => a / b;
    const a = 10;
    const b = 5;
    const resultText = `
      <strong>Function Declaration (<code>add</code>)</strong>: ${a} + ${b} = ${add(a, b)}<br>
      <strong>Function Expression (<code>multiply</code>)</strong>: ${a} × ${b} = ${multiply(a, b)}<br>
      <strong>Arrow Function (<code>divide</code>)</strong>: ${a} ÷ ${b} = ${divide(a, b)}
    `;
    document.getElementById("output").innerHTML = resultText;
  </script>
</body>
</html>
**2A**
CounterApp.js
import React, { Component } from 'react';
class CounterApp extends Component {
  constructor() {
    super();
    this.state = { count: 0 };
  }
  incrementCount = () => {
    this.setState({ count: this.state.count + 1 });
  };
  inDecrement = () => {
      this.setState({ count:this.state.count - 1});
  };
  render() {
    return (
      <div className="counter-container">
        <h1 className="counter-title">Counter: {this.state.count}</h1>
        <button
          className="counter-btn"
          onClick={this.incrementCount}
          disabled={this.state.count === 10}
        >
          +
        </button>
        <button
          className="counter-btn"
          onClick={this.decrementCount}
          disabled={this.state.count === 0}
        >
          -
        </button>
      </div>
    );
  }
}
export default CounterApp;
APP.css
.counter-container {
  text-align: center;
  margin-top: 50px;
  padding: 40px 0;
  background: #f6f9fc;
  border-radius: 16px;
  width: 340px;
  margin-left: auto;
  margin-right: auto;
  box-shadow: 0 6px 18px rgba(25,50,100,0.13);
}
.counter-title {
  color: #2b388f;
  margin-bottom: 20px;
  font-size: 2rem;
  font-family: 'Segoe UI', sans-serif;
}
.counter-btn {
  margin: 0 12px;
  padding: 10px 28px;
  font-size: 1.4rem;
  border: none;
  border-radius: 5px;
  background: #217af7;
  color: #fff;
  cursor: pointer;
  font-family: inherit;
  transition: background 0.18s;
}
.counter-btn:disabled {
  background: #b2c7ec;
  color: #f7f7f7;
  cursor: not-allowed;
}
.counter-btn:hover:not(:disabled) {
  filter: brightness(0.9);
}
**2c. Write a React program to handle the button click events in functional component**

ButtonClickDemo.js
import React from 'react';

function ButtonClickDemo() {
  function handleClick() {
    alert("Button clicked using external function!");
  }

  const handleArrowClick = () => {
    alert("Button clicked using arrow function!");
  };

  const handleWithParameter = (name) => {
    alert(`Hello, ${name}!`);
  };

  const handleEventObject = (event) => {
    alert(`Button clicked! Event type: ${event.type}`);
  };

  return (
    <div className="container" style={{ padding: '20px', fontFamily: 'Arial' }}>
      <h2>React Button Click Event Examples</h2>

      <button className="btn" onClick={() => alert("Inline button clicked!")}>
        Inline Function
      </button>
      <br /><br />

      <button className="btn" onClick={handleClick}>
        External Function
      </button>
      <br /><br />

      <button className="btn" onClick={handleArrowClick}>
        Arrow Function
      </button>
      <br /><br />

      <button className="btn" onClick={() => handleWithParameter("Sanjana")}>
        Click with Parameter
      </button>
      <br /><br />

      <button className="btn" onClick={handleEventObject}>
        Event Object Handler
      </button>
    </div>
  );
}

export default ButtonClickDemo;
APP.css
.container {
  padding: 20px;
  font-family: Arial, sans-serif;
}
.btn {
  padding: 10px 20px;
  background-color: #007BFF;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 16px;
  transition: background-color 0.3s ease;
}
.btn:hover {
  background-color: #0056b3;
}
**2e. Write a React program to display text using String literals**
import React from "react";

function greet(name) {
  return `Hello ${name}, have a great day!`; // Way 5
}

function App() {
  const name = "Mounika";
  const subject = "React";

  const message = `Welcome ${name}, this is a stored template literal!`; // Way 2

  const details = `Name: ${name}
Course: ${subject}
Topic: String Literals`; // Way 3

  const a = 20, b = 10;

  return (
    <div className="container">
      <h2>{`Hello, my name is ${name}`}</h2>

      <p>{message}</p>

      <pre
        style={{
          backgroundColor: "#f0f0f0",
          padding: "10px",
          borderRadius: "8px",
        }}
      >
        {details}
      </pre>

      <h3>{`The sum of ${a} and ${b} is ${a + b}`}</h3>

      <h2>{greet(name)}</h2>

      <p>{`Today's date is ${new Date().toLocaleDateString()}`}</p>
    </div>
  );
}

export default App;
App.css
  .container {
  text-align: center;
  margin-top: 30px;
  font-family: Arial, sans-serif;
  padding: 20px;
}
h2 {
  color: #2c3e50;
}
h3 {
  color: #16a085;
}
p {
  font-size: 18px;
  color: #444;
}
.details {
  background-color: #f0f0f0;
  padding: 12px;
  border-radius: 8px;
  font-size: 16px;
  text-align: left;
  display: inline-block;
  margin-top: 10px;
}
App.js
Import ‘./App.css’;
import React, { useState } from "react";

function App() {
    let[counter, setCounter]=useState(0);
    let stock = 10;
   return(
        <div class=”wrapper’>
            <button class=”plus’ onClick = { () => {
               If(counter<stock)   {
                            setCount(counter+1)
               }
     }}>   INCREAMENT  </button>
    <p class=”counter”>  {counter} </p>
  <button class= “minus” onClick = { () =>  {
       If(counter>0)  {
           setCounter(counter-1);
    }
}}>  DECREAMENT </button>
</div>
);
}
Export default App;
App.css
.wrapper {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 40px;  /* space between INCR, 0, DECR */
  margin-top: 40px;
    background-color: "green";
}
.btn {
  padding: 12px 25px;
  font-size: 18px;
  border: 2px solid #333;
  background-color: "red";
  cursor: pointer;
  border-radius: 8px;
}

.btn:hover {
  background: #e6e6e6;
}

.counter {
  font-size: 22px;
  min-width: 50px;
  text-align: center;
  padding: 10px 15px;
  border: 2px solid #333;
  border-radius: 8px;
  background: white;
}
**  3C**
import React from "react";
const boxStyle = {
  border: "2px solid #ccc",
  padding: "10px",
  margin: "10px",
  borderRadius: "8px",
  width: "250px",
  display: "inline-block",
  verticalAlign: "top",
};
const Box = ({ title, children }) => (
  <div style={boxStyle}>
    <h2>{title}</h2>
    {children}
  </div>
);
const Student1 = ({ name, age }) => (
  <Box title="Way 1: Basic Props">
    <p>Name: {name}</p>
    <p>Age: {age}</p>
  </Box>
);
const Student2 = ({ name, age }) => (
  <Box title="Way 2: Props Destructuring">
    <p>Name: {name}</p>
    <p>Age: {age}</p>
  </Box>
);
const Student3 = ({ details: { name, age } }) => (
  <Box title="Way 3: Object as Prop">
    <p>Name: {name}</p>
    <p>Age: {age}</p>
  </Box>
);
const Student4 = ({ name, greet }) => (
  <Box title="Way 4: Function as Prop">
    <p>Name: {name}</p>
    <button onClick={greet}>Click to Greet</button>
  </Box>
);
const Student5 = ({ name, age }) => (
  <Box title="Student Info">
    <p>Name: {name}</p>
    <p>Age: {age}</p>
  </Box>
);
const Course = ({ course, duration }) => (
  <Box title="Course Info">
    <p>Course: {course}</p>
    <p>Duration: {duration}</p>
  </Box>
);
function App() {
  const studentData = { name: "Mounika", age: 21 };
  const sayHello = () => alert("Hello from Parent Component!");
  return (
    <div style={{ textAlign: "center", fontFamily: "Arial" }}>
      <h1>React Props - All Ways in One Program</h1>
      <Student1 name="Anjali" age={21} />
      <Student2 name="Bhuvana" age={23} />
      <Student3 details={studentData} />
      <Student4 name="Chaitrika" greet={sayHello} />
      <div style={{ display: "flex", justifyContent: "center", gap: "20px" }}>
        <Student5 name="Dhamini" age={26} />
        <Course course="React Development" duration="3 Months" />
      </div>
    </div>
  );
}
export default App;

**3d**
import React, { useState } from "react";

function App() {
  const [formData, setFormData] = useState({
    name: "",
    email: "",
    password: "",
  });

  // Handle input changes
  const handleChange = (e) => {
    setFormData({ ...formData, [e.target.name]: e.target.value });
  };

  // Handle form submission
  const handleSubmit = (e) => {
    e.preventDefault();
    alert(`Form Submitted!\nName: ${formData.name}\nEmail: ${formData.email}`);
  };

  return (
    <div style={{ margin: "20px", textAlign: "center" }}>
      <h2>React Form Example</h2>
      <form onSubmit={handleSubmit} style={{ display: "inline-block", textAlign: "left" }}>
        <div style={{ marginBottom: "10px" }}>
          <label>Name: </label><br />
          <input
            type="text"
            name="name"
            value={formData.name}
            onChange={handleChange}
            required
          />
        </div>

        <div style={{ marginBottom: "10px" }}>
          <label>Email: </label><br />
          <input
            type="email"
            name="email"
            value={formData.email}
            onChange={handleChange}
            required
          />
        </div>

        <div style={{ marginBottom: "10px" }}>
          <label>Password: </label><br />
          <input
            type="password"
            name="password"
            value={formData.password}
            onChange={handleChange}
            required
          />
        </div>

        <button type="submit">Submit</button>
      </form>

      <h3>Form Data Preview:</h3>
      <p><strong>Name:</strong> {formData.name}</p>
      <p><strong>Email:</strong> {formData.email}</p>
    </div>
  );
}
export default App;





**4. Introduction to Git and GitHub **

Setup 

Install Git on local machine. 

Configure Git (user name, email). 

Create GitHub account and generate a personal access token. 

Key Steps to Install Git on Windows 

Download: Visit https://git-scm.com/download/win and download the Git installer. 

Run Installer: Double-click the downloaded file and start the setup wizard. 

Default Settings: Click Next through the wizard, accept license, and leave settings as default unless instructed otherwise. 

Install: Confirm the location and components, then click Install. 

Finish: Complete the wizard and click Finish to exit. 

Verify: Open Git Bash or Command Prompt, type git --version to confirm installation 

 

Configuration Commands – 

git config --global user.name "Your Name" 

git config --global user.email "your.email@example.com" 

 

Steps 

Open Git Bash or Command Prompt. 

Enter both commands (replacing with your actual name and email). 

To check, use: 

git config –list 

 

Creating a GitHub Account 

Open GitHub sign-up page: 

Navigate to https://github.com/join or https://github.com/ in a web browser. 

Fill in account details: 

Enter a unique username (visible publicly). 

Provide a valid email address. 

Create a secure password (minimum 15 characters or at least 8 characters with a number and lowercase letter). 

Click "Create account" or "Continue" after filling the details 

Verify you are human: 

Complete the CAPTCHA test. 

Verify your email: 

GitHub will send a verification email. 

Open the email and click the verification link or enter the code on GitHub. 

Complete setup: 

Optionally, provide some profile information. 

You can skip or complete user personalization. 

 

Generating a GitHub Personal Access Token (PAT) 

Log in to your GitHub account. 

Open Settings: 

Click your profile photo at the top-right. 

Select Settings from the dropdown menu. 

Access Developer Settings: 

In the sidebar, scroll down and click Developer settings. 

Select Personal Access Tokens: 

Click on Personal access tokens. 

Then click Tokens (classic) (or the available token option). 

Generate a new token: 

Click Generate new token button. 

Re-enter your GitHub password if prompted. 

Configure the token: 

Add a descriptive Note for the token (e.g., "Exam token"). 

Set Expiration (e.g., No expiration or a set duration). 

Select the necessary scopes/permissions (e.g., repo, workflow) depending on your use case. 

Click Generate token to create the token. 

Copy the token immediately: 

This token is shown only once. Save it securely. 

Use this token as your password for Git authentication instead of your GitHub password. 

 

** 4b**

Basic Git Workflow 

Step 1: Initialize Local Repository 

git init 

This creates a new empty Git repository in the current folder. 

Step 2: Create a File using nano 

nano file1.txt 

Type some content (example: Hello Git using nano editor) 

Press CTRL + O → Enter (to save) 

Press CTRL + X (to exit nano) 

 

 Repeat for more files: 
nano file2.txt 

 

Step 3: Add Files to Staging Area 

git add . 

This adds all created files (file1.txt, file2.txt, etc.) to the staging area. 

 

Step 4: Check Status 

git status 

Confirms that files are staged and ready for commit. 

  

 

Commit files 

Command: 

git commit -m "Initial commit" 

his saves your changes into the local repository with a commit message ("Initial commit"). 

Connect local repo to GitHub (Remote Repository) 

Command: 

git remote add origin <repo_url> 

<repo_url> is the HTTPS/SSH link of your GitHub repository. 

Example: 

git remote add origin https://github.com/username/repository.git 

Push files to GitHub 

Command: 

git push -u origin master 

 

 
**4c**
Branching and Collaboration 

 

The command git checkout -b feature1 is used in Git to create a new branch named "feature1" and switch (checkout) to this newly created branch immediately. 

Command Breakdown 

git: The command-line tool for Git version control. 

checkout: The Git command used to switch from one branch to another. 

-b: An option that tells Git to create a new branch before switching to it. 

feature1: The name of the new branch you want to create. 
 

1. Create a Branch 

Use the command: 

git checkout -b feature1 

Explanation: 

Creates a new branch named feature1. 

Switches to the newly created branch immediately. 

This isolates new feature work from the main branch. 

 

2. Work on the Feature Branch 

Make changes and commit them: 

git add . 

git commit -m "Implemented feature1 changes" 

This records your changes in the feature1 branch. 

 

3. Switch Back to Main Branch 

Before merging, switch back to main: 

git checkout main 

Ensures main is the active branch for merging. 

 

4. Merge the Feature Branch into Main 

Merge feature1 into main: 

git merge feature1 

This incorporates the changes from feature1 into main. 

If no conflicting changes exist, the merge completes automatically. 

 

5. Resolve Merge Conflicts (If Any) 

When Git cannot automatically merge files due to conflicting changes, it marks the conflict in the affected files. Follow these steps: 

a. Identify Conflicts 

Git will show the conflicting files after the merge. 

Use: 

git status 

to see conflicted files listed as "both modified". 

 

b. Open Conflicted Files 

Conflicts are marked with special markers: 

<<<<<<< HEAD 

Your changes on the main branch 

======= 

Changes from feature1 branch 

>>>>>>> feature1 

Edit the file to choose which code to keep or combine parts as needed. 

 

c. Stage Resolved Files 

After editing and saving, mark conflicts as resolved by staging: 

git add <filename> 

 

d. Complete the Merge Commit 

Commit the merge to finalize: 

git commit 

Git may auto-populate the commit message for the merge; save and close the editor. 

Summary Workflow Commands 

 

# Create and switch to feature branch 

git checkout -b feature1 

 

# Work on feature, add and commit changes 

git add . 

git commit -m "Add new feature1" 

 

# Switch back to main branch 

git checkout main 

 

# Merge feature branch into main 

git merge feature1 

 

# If merge conflict occurs: 

# 1. Check status and edit conflicted files 

git status 

# 2. Edit files to resolve conflicts 

# 3. Stage resolved files 

git add <filename> 

# 4. Complete merge commit 

git commit 

 
