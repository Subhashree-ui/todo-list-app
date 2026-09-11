<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My To-Do list</title>
</head>
<body>
    <h1 id="heading"> My To-Do List</h1>
    <input type="text" id="taskInput"  placeholder="Enter a task">
    <button id="addButton"> Add Task</button>

    <ul id="taskList"></ul>

    <script>
        let input = document.getElementById("taskInput");
        let addButton = document.getElementById("addButton");
        let taskList = document.getElementById("taskList")

        addButton.addEventListener("click", function(){
            if(input.value ===""){
                alert ("please enter a task ");
                return;
            }

            let li = document.createElement ("li");
            li.textContent = input.value;

            let deleteBtn= document.createElement("button");
            deleteBtn.textContent ="delete"

            deleteBtn.addEventListener("click", function(event){
                event.stopPropagation();
                li.remove();
            });

            li.addEventListener("click", function(){
                if( li.style.textDecoration === "line-through"){
                    li.style.textDecoration = "none";
                } else{
                    li.style.textDecoration = "line-through";
                }

            });

            li.appendChild(deleteBtn);
            taskList.appendChild(li);
            input.value = "";
        });
    </script>
</body>
</html> 
