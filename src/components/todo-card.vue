

<template>

  <div class="card">
    <header class="card-header">
      <p class="card-header-title is-centered">
        {{ now }}
      </p>
      <p class="card-header-title is-centered">
        {{titre}}
      </p>
      <p class="card-header-title is-centered">
        {{tasks.length}} taches
      </p>
    </header>


    <div class="card-content">
      <div class="content">
          <new-todo v-on:ajoutertask="addTask"></new-todo>            


  <ul>
    <li>
      <todo-list
      v-for="(task, index) in tasks"
      v-bind:key="task.id"
      v-bind:title="task.title"
      v-on:remove="tasks.splice(index, 1)"> </todo-list></li>
  </ul>


      </div>
    </div>
   
  </div>



</template>
  
  <script>
  import NewTodo from "./new-todo.vue";
  import TodoList from "./todo-list.vue";
  
  export default {
   
    data() {
        return {
            titre: 'VueJs Tutorial ToDo List',
            newTaskText: '',
    tasks: [
      {
        id: 1,
        title: 'oui',
      },
      {
        id: 2,
        title: 'non',
      },
      
    ],
    nextTaskId: 3
        };
        
    },
    components: {
      NewTodo,
      TodoList
    },
  
         methods: {
        addTask(task) {
            this.tasks.push({description: task, check:false})
            
        },
       
    },
    computed: {
        now: function () {
            return new Date().toDateString();
        }
    },
  
  }

  </script>
<style>
 .card-header {
     font-size: 18px;
     font-weight: 700;
     color: #363636;
 }
</style>

