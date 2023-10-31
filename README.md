<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8">
	<meta name="viewport" content="width=device-width, initial-scale=1">
	<style>
		body{
			font-family: Arial;
			background-color: lightpink;
			margin: 0;
			display: flex;
			justify-content: center;
			align-items: center;
			height: 100vh;
		}
		.container{
			text-align:center;
			}
		#app{
			margin-top:20px;
			}
		ul {
			list-style-type: none;
			padding: 0;
		}
		li {
			background-color: #fff;
			padding: 10px;
			margin: 5px 0;
			border-radius: 5px;
			display: flex;
			justify-content: space-between;
			align-items: center;
		}
		li button {
			background-color: gold;
			color: black;
			border: none;
			padding: 5px 12px;
			border-radius: 3px;
			cursor: pointer;
		}
	</style>
	<title> To Do List </title>
</head>
<body>
	<div class="container">
		<h1>To Do List </h1>
		<div id="app">
			<input type="text" id="taskInput" placeholder ="add a new task">
			<button onclick="addTask()"> Add </button>
			<ul id="taskList"></ul> 
		</div>
	</div>
	<script>
	 function addTask(){
	  const taskInput=document.getElementById("taskInput");
	  const taskList=document.getElementById("taskList");

			if (taskInput.value.trim() !== "") {
        	const li = document.createElement("li");
        	li.innerHTML = `
          <span>${taskInput.value}</span>
          <button onclick="removeTask(this)">Remove</button>
        `;
        taskList.appendChild(li);
        taskInput.value = "";
      }
    }

    function removeTask(button) {
      const li = button.parentNode;
      const taskList = document.getElementById("taskList");
      taskList.removeChild(li);
	}
	</script>
</body>
</html>
