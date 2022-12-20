<template>
<div class="">
  <div :class="[todoProps.complete ? 'complete' : '']">
    <div class="todo-item" >
      <div class="checkbox">
      <input type="checkbox" :checked="todoProps.complete" @change="markItem" />
      {{ todoProps.title }}
      </div>
      <div class="btn-del">
      <button @click="deleteTodo" class="del-btn">Delete</button>
    </div></div>
  </div>
  </div>
</template>

<script>
import { ref } from "vue";
export default {
  name: "TodoItem",
  props: ["todoProps"],
  setup(props, context) {
    const markItem = () => {
      context.emit("mark-complete", props.todoProps.id);
    };

    const deleteTodo = () => {
      context.emit("delete-complete", props.todoProps.id);
    };

    return {
      markItem,
      deleteTodo,
    };
  },
};
</script>

<style>
.complete {
  display: none;
}
.todo-item{
  display: flex;
      padding: 5px 0;
}
.checkbox{
  
    width: 60%;

}
</style>