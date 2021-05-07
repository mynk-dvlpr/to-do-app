# to-do-app

#index.html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TO-DO App</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container">
        <h1>TO-DO List</h1>
        <div class="add-element">
            <input type="text" id = "add" placeholder ="Type something to do">
            <button id="btn">Add</button>
        </div>

        <div class="element-list">
            <ul id="list">
                <li>Attend the class at 9:00 am</li>
                <li>Do the Programming </li>
            </ul>
        </div>
    </div>
</body>
<script src="main.js"></script>
</html>

#style.css
*{
    margin: 0;
    padding: 0;
    outline: 0;
}

body{
    background-color: #eceff1;
}

.container{
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    background-color: #fafafa;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 1);
    width: 460px;
    height: 600px;
    text-align: center;
    font-family: 'Nunito',sans-serif;
}

h1{
    margin: 12px 0;
}

.add-element{
    margin: 12px 0;
}

input{
    padding: 6px 4px;
    width: 70%;
}

button{
    padding: 7px 14px;
    background-color: royalblue;
    border: none;
    border-radius: 4px;
    color: #fafafa;
}

.element-list{
    height: 550px;
    overflow-y: auto;
}
ul{
    padding: 15px;
}

li{
    list-style: none;
    padding: 10px 5px;
    background-color: #fff;
    margin: 12px 0;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 1);
    border-radius: 3px;
    transition: .4s;
}

button:hover{
    background-color: #1565c0;
}

li:hover{
    background-color: #e0e0e0;
}

.checked{
    text-decoration: line-through;
    background-color: #e0e0e0;
}


#main.js
let input = document.querySelector('#add');
let btn = document.querySelector('#btn');
let list = document.querySelector('#list');
let el = document.getElementsByTagName('li');


btn.addEventListener('click',() =>{
    let txt = input.value;
    if(txt === ""){
        alert("You must write something");
    }else{
        let li = document.createElement('li');
        li.innerHTML = txt;
        list.insertBefore(li, list.childNodes[0]);
        input.value = '';
    }

})

list.addEventListener('click', e =>{
    if (e.target.tagName == 'LI'){
        e.target.classList.toggle('checked');
    }
})
