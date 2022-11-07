<template>
  <div class="container" >
    <Header/>


  <div class="viewed-tasks">
    <div class="task">
      <h2>Create a Todo App </h2>
      <button>x</button>
    </div>
    <div class="task">
      <h2> Have CRUD functionality on it </h2>
      <button>x</button>
    </div>
  </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage'

}
</script>

<style lang="scss" scoped >
  .container{
    max-width:  1200px;
    margin: 0 auto;
    height: 100%;
    border-left: 2px solid black;
  }
  .viewed-tasks{
    display: flex;
  
    flex-direction: column;
    align-items: flex-start;
    margin-top: 5rem;
    gap: 2rem;
    button{
      background-color: rgba(0, 0, 0, 0);
      padding: .5rem;
      color: rgb(249, 115, 115);
      border: none;
      cursor: pointer;
      font-size: 1rem;
      font-weight: 800;
    }

  }


  .task{
    color: white;
    background-color: rgb(39, 39, 39);
    padding: 1rem 5rem;
    display: flex;
    align-items: center; 
    gap: 4rem;

  }

</style>
