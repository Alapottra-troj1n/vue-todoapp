<template>
  <div class="container">
    <Header :todos="todos" @newTaskData="addNewTask"  />


    <div class="viewed-tasks">

      <div v-for="todo of todos" :key="todo.id" class="task">
        <h2>{{ todo.task }}</h2>
        <button @click="handleDelete(todo)" >x</button>
      </div>

    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage'

  ,

  data() {

    return {

      todos: [{ id: 1, task: 'Create a Todo App' }, { id: 2, task: 'Make CRUD functionality within the app ' }]

    }
  },

  methods: {

      addNewTask(newTask) {
        
        this.todos = [...this.todos, newTask]

      },
      handleDelete(todo){
        
       this.todos = this.todos.filter(task => task.id !== todo.id )

      }

  }

}
</script>

<style lang="scss" scoped >
.container {
  max-width: 1000px;
  margin: 0 auto;
  height: 100%;
  border-left: 2px solid black;

}

.viewed-tasks {
  display: flex;

  flex-direction: column;
  align-items: flex-start;
  margin-top: 5rem;
  gap: 2rem;

  button {
    background-color: rgba(0, 0, 0, 0);
    padding: .5rem;
    color: rgb(249, 115, 115);
    border: none;
    cursor: pointer;
    font-size: 1rem;
    font-weight: 800;
  }

}


.task {
  color: white;
  background-color: rgb(39, 39, 39);
  padding: 1rem 5rem;
  display: flex;
  align-items: center;
  gap: 4rem;

}
</style>
