<template>
  <div>
    <input class="add-input" type="text" v-model="title">
    <input class="add-btn" @click="addItem" type="submit" value="Add">
  
  </div>
</template>

<script>
import {ref} from 'vue'
export default {
 setup(props, context) {
    const title =ref('')
const addItem = () =>{
  
    const newItem ={
        id:Date.now(),
        title:title.value,
        complete:false
    }
    console.log(context)
    context.emit('add-todo',newItem)//ham số thứ nhất là tên sự kiện do ta tự đặt, tham số thứ 2 là giá trị muốn update.
 title.value=''
}

    return{
        title,
        addItem
    }
 }
}
</script>

<style>
.add-btn{
       border-radius: 5px;
    color: #fff;
    background-color: #ef6464;
    border: none;
    padding: 7px 10px;
    margin: 0 5%;

}
.add-btn:hover{
    background-color: red;
}
.add-input{
    width: 70%;
    padding: 5px 0;
}
</style>