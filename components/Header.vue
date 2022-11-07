<template>
    <div>
        <h2><span class="logo">Jasper</span> Todo App</h2>


        <div class="addTask">
            <input v-model="inputTask" placeholder="Write Task" />
            <button>ADD TASK</button>
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


}


</script>

<style lang="scss" scoped>
.logo {
    color: #F72585;
}

h2 {
    margin-top: 1rem;
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