<template>
<div class="">
  <div v-if="todoProp.complete === true" class="comp">
    <div class="comp-item">
       {{ todoProp.title }}
       </div>
       <div class="comp-btn">
        <button  @click="deleteComp" >Delete</button> 
        </div>
  </div>
</div>
</template>

<script>
export default { 
  props: ["todoProp"],
  setup(props, context) {
    const deleteComp = () => {
      context.emit("delete-comp", props.todoProp.id);
    };
   return { 
      deleteComp,
    };
  },
};
</script>

<style>
.comp{
  display: flex;
}
.comp-item{
      width: 60%;
}
button{
  background-color:#ef6464;
  padding: 7px 10px;
  border: none;
  border-radius: 5px;
}
</style>