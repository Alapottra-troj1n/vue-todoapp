<template>
    <div>
        <h2><span class="logo">JASPER</span> TODO</h2>


        <div class="addTask">
            <input v-model="inputTask" placeholder="Write Task" />
            <button @click="handleAddTask" >ADD TASK</button>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Header'
    ,

    data() {
        return {
         inputTask: ''
        }
    },
    props: [
        "todos"
    ],
    methods: {
        handleAddTask(){

           const newTask = {
            id : this.todos.length + 1,
            task : this.inputTask
           }

           this.$emit('newTaskData', newTask);

           this.inputTask = ''




        }
    }


}


</script>

<style lang="scss" scoped>
.logo {
    color: #f81e30;
}

h2 {
   padding-top: 2rem;
    text-align: center;
    font-size: 2rem;
}

.addTask{
    display: flex;
    justify-content: center;
    margin-top: 6rem;
    input{
        width: 30rem;
        padding: 1rem .8rem;
    }
}
</style>