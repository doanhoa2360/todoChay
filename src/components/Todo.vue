<template>
  <div>
    <AddTodo @add-todo="addTodo" />
    <div>
      <TodoItem
        v-for="todo in todos"
        :key="todo.id"
        :todoProps="todo"
        @mark-complete="markItem"
        @delete-complete="deleteItem"
      />
    </div>
    <button @click="deleteAll">DeleteAll</button>
    <h1>Complete</h1>
   <CompleteItem  v-for="tod in todos" :key="tod.id"  :todoProp="tod" @delete-comp="delComp"/>
  </div>
</template>

<script>
import { ref } from "vue";
import TodoItem from "./TodoItem.vue";
import AddTodo from "./AddTodo.vue";
import CompleteItem from "./CompleteItem.vue"
export default {
  name: "Todo",
  components: { TodoItem, AddTodo, CompleteItem },

  setup() {
    const todos = ref([
      {
        id: 0,
        title: " viec 1",
        complete: false,
      },
      {
        id: 1,
        title: " viec 2",
        complete: false,
      },
      {
        id: 2,
        title: " viec 3",
        complete: false,
      },
    ]);

    const addTodo = (newTodo) => {
      todos.value.push(newTodo);
      console.log(todos.title);
    };
    const markItem = (id) => {
      todos.value = todos.value.map((todo) => {
        if (todo.id === id) todo.complete = !todo.complete;
        {
          return todo;
        }
      });
    };
const delComp = (id)=>{
   todos.value = todos.value.filter((todo) => todo.id !== id);
}
    const deleteItem = (id) => {
      todos.value = todos.value.filter((todo) => todo.id !== id);
    };
    const deleteAll = () => {
      todos.value = [];
    };

    return {
      todos,
      addTodo,
      deleteItem,
      delComp,
      deleteAll,
      markItem,
    };
  },
};
</script>

<style>
</style>