# Ex03 To-Do List using JavaScript
## Date: 05/12/2026

## AIM
To create a To-do Application with all features using JavaScript.

## ALGORITHM
### STEP 1
Build the HTML structure (index.html).

### STEP 2
Style the App (style.css).

### STEP 3
Plan the features the To-Do App should have.

### STEP 4
Create a To-do application using Javascript.

### STEP 5
Add functionalities.

### STEP 6
Test the App.

### STEP 7
Open the HTML file in a browser to check layout and functionality.

### STEP 8
Fix styling issues and refine content placement.

### STEP 9
Deploy the website.

### STEP 10
Upload to GitHub Pages for free hosting.

## PROGRAM

### index.html
```html
<!-- index.html -->

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aqua Todo App</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <!-- Background Circles -->
    <div class="circle circle1"></div>
    <div class="circle circle2"></div>
    <div class="circle circle3"></div>

    <div class="todo-container">

        <h1>Todo List</h1>

        <div class="input-box">
            <input type="text" id="taskInput" placeholder="Enter your task">
            <button onclick="addTask()">Add</button>
        </div>

        <ul id="taskList"></ul>

    </div>

    <script src="script.js"></script>

</body>
</html>
```

### style.css

```css
/* style.css */

*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family: Arial, Helvetica, sans-serif;
}

body{
    height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    background: linear-gradient(135deg,#00f7ff,#ff00bb,#00ffff);
    overflow:hidden;
    position:relative;
}

.todo-container{
    width:500px;
    padding:30px;
    border-radius:25px;
    background: rgba(255,255,255,0.12);
    backdrop-filter: blur(15px);
    box-shadow:0 10px 30px rgba(0,0,0,0.4);
    border:1px solid rgba(255,255,255,0.2);
    z-index:10;
}

h1{
    text-align:center;
    margin-bottom:25px;
    color:white;
    font-size:40px;
    letter-spacing:1px;
}

/* Input */

.input-box{
    display:flex;
    gap:10px;
    margin-bottom:25px;
}

.input-box input{
    flex:1;
    padding:14px;
    border:none;
    border-radius:12px;
    outline:none;
    background: rgba(255,255,255,0.15);
    color:white;
    font-size:16px;
}

.input-box input::placeholder{
    color:#dbeafe;
}

.input-box button{
    padding:14px 22px;
    border:none;
    border-radius:12px;
    background:#00e5ff;
    color:#003566;
    font-weight:bold;
    cursor:pointer;
    transition:0.3s;
}

.input-box button:hover{
    transform:scale(1.05);
    background:#7df9ff;
}

/* Task List */

ul{
    list-style:none;
}

li{
    background: rgba(255,255,255,0.15);
    margin-bottom:15px;
    padding:15px;
    border-radius:15px;
    display:flex;
    justify-content:space-between;
    align-items:center;
    color:white;
    transition:0.3s;
}

li:hover{
    transform:translateY(-3px);
}

/* Task Text */

.task-text{
    font-size:18px;
    font-weight:bold;
}

/* Buttons */

.btn-group{
    display:flex;
    gap:8px;
}

.complete-btn,
.edit-btn,
.delete-btn{
    border:none;
    padding:8px 12px;
    border-radius:10px;
    cursor:pointer;
    font-weight:bold;
    transition:0.3s;
}

.complete-btn{
    background:#00ffbf;
    color:#003566;
}

.complete-btn:hover{
    background:#7cffcb;
}

.edit-btn{
    background:#38bdf8;
    color:white;
}

.edit-btn:hover{
    background:#0ea5e9;
}

.delete-btn{
    background:#ff4d6d;
    color:white;
}

.delete-btn:hover{
    background:#e63946;
}

/* Completed Task */

.completed{
    text-decoration: line-through;
    opacity:0.6;
    color:#d1d5db;
}
```


### script.js

```javascript
// script.js

function addTask(){

    let input = document.getElementById("taskInput");

    let taskText = input.value.trim();

    if(taskText === ""){
        alert("Please enter a task");
        return;
    }

    let li = document.createElement("li");

    li.innerHTML = `
    
        <span class="task-text">
            ${taskText}
        </span>

        <div class="btn-group">

            <button class="complete-btn" onclick="completeTask(this)">
                Complete
            </button>

            <button class="edit-btn" onclick="editTask(this)">
                Edit
            </button>

            <button class="delete-btn" onclick="deleteTask(this)">
                Delete
            </button>

        </div>
    `;

    document.getElementById("taskList").appendChild(li);

    input.value = "";
}

/* Complete Task */

function completeTask(button){

    let task = button.parentElement.parentElement.querySelector(".task-text");

    task.classList.toggle("completed");

    if(task.classList.contains("completed")){
        button.innerText = "Undo";
    }
    else{
        button.innerText = "Complete";
    }
}

/* Delete Task */

function deleteTask(button){
    button.parentElement.parentElement.remove();
}

/* Edit Task */

function editTask(button){

    let task = button.parentElement.parentElement.querySelector(".task-text");

    let newTask = prompt("Edit your task", task.innerText);

    if(newTask !== null && newTask.trim() !== ""){
        task.innerText = newTask;
    }
}
```
## OUTPUT


<img width="1905" height="1033" alt="image" src="https://github.com/user-attachments/assets/2d4fa559-d6bf-44be-be96-ef0868059835" />



## RESULT
The program for creating To-do list using JavaScript is executed successfully.
