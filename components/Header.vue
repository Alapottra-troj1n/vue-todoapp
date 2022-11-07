<template>
    <div>
        <h2><span class="logo">NUXT</span> TODO</h2>


        <div class="addTask">
            <input v-model="inputTask" placeholder="Write Task" />
            <button @click="handleAddTask" >ADD TASK</button>
        </div>
        <p>{{error}}</p>
    </div>
</template>

<script>
export default {
    name: 'Header'
    ,

    data() {
        return {
         inputTask: '',
         error: ''
        }
    },
    props: [
        "todos"
    ],
    methods: {
        handleAddTask(){
            if(this.inputTask === ''){
                this.error= 'Error ! Invaild input field '
                return;
            }
           const newTask = {
            id : this.todos.length + 1,
            task : this.inputTask
           }

           this.$emit('newTaskData', newTask);
           this.error= ''
           this.inputTask = ''




        }
    }


}


</script>

<style lang="scss" scoped>
.logo {
    color: #17bd59;
}

h2 {
   padding-top: 2rem;
    text-align: center;
    font-size: 2rem;
}
p{
    text-align: center;
    margin-top: 1rem;
    color: red;
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