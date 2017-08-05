<!DOCTYPE html>
    <html>
    <head>
        <title>Hello</title>
        <link rel="stylesheet" type="text/css" href="stylesheetV2.css" />
        <link rel="stylesheet" type="text/css" href="todo.css" />
        <link href="https://fonts.googleapis.com/css?family=Orbitron" rel="stylesheet" />
        <style>
            body {
                background: url("background.gif") no-repeat center center fixed;
                background-size: cover;
                -moz-background-size: cover;
                -webkit-background-size: cover;
            }

            #centered {
                position: absolute;
                top: 25%;
                left: 53%;
                /* bring your own prefixes */
                transform: translate(-50%, -50%);
            }

            .content-container{
                position: absolute;
                top: 37%;
                left: 53.5%;
                transform: translate(-50%, -50%);
            }

            .content{
                position: flex;
            }

            .hide{display: none;}

            .icons{
                display: flex; 
                flex-direction: column;
                justify-content: center;
                margin: 25px 40px;
                flex-direction: row;
                align-content: flex-start;
            }
            .container{
                width: 75px;
                height: 75px;
                margin: 15px;
            }

            .container img{
                width: 100%;
                height: auto;
                opacity: .5;
            }


            img:hover{
                opacity: .7;
            }

            h1{
                font-family: 'Orbitron', sans-serif;
                color: #d3d3d3;
                opacity: .6;
                border-bottom: 3px solid;
                text-align: center;
                text-shadow: -1px -1px 0  #000, 1px -1px 0  #000, -1px 1px 0  #000, 1px 1px 0  #000;
                z-index: 1;
                
            }

            .items, a{
                display: flex;
                text-decoration: none;

            }
            .items{
                list-style: none;
            }
            li{
                color:  #d3d3d3;
                margin:0 20px;
                text-shadow: -1px -1px 0  #000, 1px -1px 0  #000, -1px 1px 0  #000, 1px 1px 0  #000;
                font-size: 25px;
                font-family: 'Orbitron', sans-serif;
                opacity: .6;
                
            }

            button{
                background-color: transparent;
                color: #d3d3d3;
                border: none;
                opacity: .8;
                font-family: 'Orbitron', sans-serif;
                font-size: 16px;
                margin:auto;
                z-index: 1;
            }
            input{
                margin:auto;
                width: 20px;
                font-size: 12px;
                font-family: 'Orbitron', sans-serif;
                background-color: transparent;
                border: none;
                border-bottom: 2px solid #d3d3d3;   color: #d3d3d3;
                z-index: 1;
            }

            #todo-text{
                width: 120px;
            }
            #new-todo-text{
                width: 90px;
            }

            #todos, #todos li{
                font-family: 'Orbitron', sans-serif;
                font-size: 12px;
                display: block;
                max-height: 25px;
            }

            .deleteButton{
                font-family: 'Orbitron', sans-serif;
                font-size: 12px;
                border: none;
                color: #d3d3d3;
                opacity: .8;
                text-shadow: -1px -1px 0  #000, 1px -1px 0  #000, -1px 1px 0  #000, 1px 1px 0  #000;

            }
        </style>
    </head>

    <body>
        <div id="centered">
            <div class="row icons">
                <div id="checklist" class="container show"><img id="checklistIcon" class="image" src="images/checklist.png" /></div>
                <div id="chan" class="container show"><img id="clover" class="image" src="images/4chan.png" /></div>
                <div id="music" class="container show"><img id="musicIcon" class="image" src="images/music.png" /></div>
                <div id="school" class="container show"><img id="schoolIcon" class="image" src="images/school.png" /></div>
                <div id="work" class="container show"><img id="workIcon" class="image" src="images/work.png" /></div>
                <div id="resources" class="container show"><img id="resourceIcon" class="image" src="images/book.png" /></div>
            </div>
        </div>
        <div class="content-container">
           <div class="content hide" id="todoList">
               <h1 class="stay">Tasks</h1>
               <div class="stay">
                <input type="text" id="todo-text" placeholder="Max of 10 Inputs"/>
                <button onclick="handlers.addTodo()">Add</button>
                <input type="text" id="new-todo-text" placeholder="Change Item" />
                <input type="number" id="position" placeholder="Item#" />
                <button onclick="handlers.changeTodo()">Change</button>
                <input type="number" id="toggle-position" />
                <button onclick="handlers.toggleTodo()">Toggle</button>
            </div>
            <div id="todos">
                <ul></ul>
            </div>
        </div>
        <div class="content hide" id ="4chanList">
            <h1>4Chan</h1>
            <ul class="items">
                <a href="boards.4chan.org/an"><li>/an/</li></a>
                <a href="boards.4chan.org/ck"><li>/ck/</li></a>
                <a href="boards.4chan.org/diy"><li>/diy/</li></a>
                <a href="boards.4chan.org/fit"><li>/fit/</li></a>
                <a href="boards.4chan.org/g"><li>/g/</li></a>
                <a href="boards.4chan.org/wg"><li>/wg/</li></a>
            </ul>
        </div>
        <div class="content hide" id="musicList">
            <h1>Music</h1>
            <ul class="items">
                <a href="https://www.youtube.com/playlist?list=PLs7d4DToZ-osYBxLSjaGB3Wlv1E6Wvscj"><li>F-Funk</li></a>
                <a href="https://play.google.com/music/listen#/pl/AMaBXynTfmdsy_K0RZDICeMWNkZtUTNPc142DpaDNts4Q1EDnz2KBMP3JQEd04JP4cBZOlEf3_xWhhZZNpl6kUDiseRamCleug%3D%3D"><li>Synth</li></a>
                <a href="https://www.youtube.com/playlist?list=PLs7d4DToZ-ot1Kg6Up1fBW5Zfa_Vi4f-8"><li>Eurobeat</li></a>
                <a href="https://www.youtube.com/playlist?list=PLs7d4DToZ-ovEUtKLAaLI2Cz_UpNUt35A"><li>Comfy</li></a>
                <a href="https://play.google.com/music/listen#/wmp"><li>Play</li></a>
            </ul>
        </div>
        <div class="content hide" id="schoolList">
            <h1>School</h1>
            <ul class="items">
                <a href=""><li>Email</li></a>
                <a href=""><li>Billing</li></a>
                <a href=""><li>Class</li></a>
            </ul>
        </div>
        <div class="content hide" id="workList">
            <h1>Work</h1>
            <ul class="items">
                <a href="https://github.com/"><li>Github</li></a>
                <a href="https://mail.google.com/mail/u/0/#inbox"><li>Gmail</li></a>
                <a href="https://www.dropbox.com/"><li>DropBox</li></a>
            </ul>
        </div>
        <div class="content hide" id="resourceList">
            <h1>Resources</h1>
            <ul class="items">
                <a href="https://developer.mozilla.org/en-US/"><li>MDN</li></a>
                <a href="https://css-tricks.com/"><li>CSS</li></a>
                <a href="http://stackoverflow.com/"><li>Stack</li></a>
                <a href="https://www.dropbox.com/sh/dcf2gui0jkvucxq/AACYc8QhwBgP4zoU4ndsauFda?dl=0"><li>Unix</li></a>
                <a href="bento.io"><li>Path</li></a>
                <a href="https://www.smashingmagazine.com/"><li>Studies</li></a>
            </ul>
        </div>
    </div>
    <script type="text/javascript">
        var todoList = {
            todos: [],

    addTodos: function(todoText){ //add todo pass in hi todoText = hi addTodos('hi')

    this.todos.push({
        todoText: todoText,
        completed: false
    });

},
changeTodos: function(position, todoText){
        //this.todos[position] = todoText;

        this.todos[position].todoText = todoText;
    },
    removeTodos: function(position){
        this.todos.splice(position, 1);
    },
    toggleCompleted: function(position){
        var todo = this.todos[position];
        todo.completed = !todo.completed;

    },

    toggleAll: function(){
        var totalTodos = this.todos.length;
        var completedTodos = 0;

        //get number of completed todos

        /*for(var i = 0; i < totalTodos; i++){
            if(this.todos[i].completed === true){
                completedTodos++;
            }
        }*/

        this.todos.forEach(function(todo){
            if(todo.completed === true){
                completedTodos++;
            }
        });
        //if true make everything false and vice versa

        this.todos.forEach(function(todo){
            if(completedTodos == totalTodos){
                todo.completed = false;
            }else{
                todo.completed = true;
            }
        });
    }
};

//new code THIS IS EXACTLY THE SAME AS THE CODE ABOV BUT IT'S MORE EFFICIENT AND EASIER TO READ

var handlers = {
    displayTodos: function(){
        todoList.displayTodos();
        view.displayTodos();
    },
    toggleAll: function(){
        todoList.toggleAll();
        view.displayTodos();
    },
    addTodo: function(){
        if(todoList.todos.length > 9){
            return;
        }else{
            var addTodoText = document.getElementById('todo-text');
            todoList.addTodos(addTodoText.value);
            addTodoText.value = '';
            view.displayTodos();
        }
    },
    changeTodo: function(){
        var todoPosition = document.getElementById('position');
        var newTodoText = document.getElementById('new-todo-text');
        todoList.changeTodos(todoPosition.valueAsNumber, newTodoText.value);
        todoPosition.value = '0';
        newTodoText.value = '';
        view.displayTodos();
    },
    deleteTodo: function(position){
        todoList.removeTodos(position);
        view.displayTodos();
    },
    toggleTodo: function(position){
        var todoChangePosition = document.getElementById('toggle-position');
        todoList.toggleCompleted(todoChangePosition.valueAsNumber);
        todoChangePosition.value = '0';     
        view.displayTodos();
    }
};

var view = {
    displayTodos: function(){
        var todosUL = document.querySelector('ul');
        todosUL.innerHTML='';
        todoList.todos.forEach(function(todo, position){
            var todosLI = document.createElement('li');
            var todoComplete = '';

            if(todo.completed === true){
                todoComplete = '(O) ' + todo.todoText;
            }else{
                todoComplete = '(X) ' + todo.todoText;
            }
            todosLI.id = position;
        todosLI.textContent = todoComplete; //take todo li element, get content property and set it

        todosLI.appendChild(this.createDeleteButton());
        todosUL.appendChild(todosLI);
    }, this);
    },
    createDeleteButton: function(){
        var deleteButton = document.createElement('button');
        deleteButton.textContent = 'Delet this';
        deleteButton.className = 'deleteButton';
        return deleteButton;
    },
    createToggleButton: function(){
        var toggleButton = document.createElement('button');
        toggleButton.textContent = 'toggle';
        toggleButton.className = 'toggleButton';
        return toggleButton;
    },

    setupDeleteListener: function(){
        var todosUL = document.querySelector('ul');
        todosUL.addEventListener('click', function(event){
            console.log(event.target.parentNode.id);
            var elementClicked = event.target;
            if(elementClicked.className === 'deleteButton'){
                handlers.deleteTodo(parseInt(elementClicked.parentNode.id));
            }
        });
    },
}
view.setupDeleteListener();
</script>
<script type="text/javascript">
    
    $(function(){
        $('#chan').mouseover(function(){
            if($('.content').hasClass('active')){
                $('.content').removeClass('active').hide();
            }
            $('#4chanList').addClass('active').show('600');
        });
        $('#music').mouseover(function(){
            if($('.content').hasClass('active')){
                $('.content').removeClass('active').hide();
            }
            $('#musicList').addClass('active').show('600');

        });
        $('#school').mouseover(function(){
            if($('.content').hasClass('active')){
                $('.content').removeClass('active').hide();
            }
            $('#schoolList').addClass('active').show('600');
        });
        $('#work').mouseover(function(){
            if($('.content').hasClass('active')){
                $('.content').removeClass('active').hide();
            }
            $('#workList').addClass('active').show('600');
        });
        $('#resources').mouseover(function(){
            if($('.content').hasClass('active')){
                $('.content').removeClass('active').hide();
            }
            $('#resourceList').addClass('active').show('600');
        });

        $('#checklist').mouseover(function(){
            if($('.content').hasClass('active')){
                $('.content').removeClass('active').hide();
            }
            $('#todoList').addClass('active').show('600');
        });
    });
</script>
<script type="text/javascript" src="todo.js"></script>
<script type="text/javascript" src="jquery-3.1.1.js"></script>
<script type="text/javascript" src="homepageV2.js"></script>
</body>
</html>
