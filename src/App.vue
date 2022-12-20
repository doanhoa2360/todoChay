<template>
<div class="container">
  <Header/>
<Todo/>


</div>
</template>

<script>
import Header from './components/Header.vue'
import Todo from './components/Todo.vue'
import TodoItem from './components/TodoItem.vue'
export default {
  name: 'App',
components:{
  Header,
  Todo,
  TodoItem,
}
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;

}
.container{
      margin: auto;
    height: 100vh;
    width: 400px;
    border: 1px #000 solid;
    color: #fff;
    background-color: rgb(42, 41, 41);
}

</style>
