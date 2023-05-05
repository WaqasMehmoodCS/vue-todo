<script setup>
import {reactive, ref} from "vue"

const task=ref('')
const todos=reactive([])
const addTodo =(task)=>{
    todos.push(task)
// console.log(todos)       
    }
    const del = (t,i)=>{
        todos.splice(i,1)
console.log(t)
console.log(i)
    }
</script>
<template>
<div>
<h1>TODO LIST</h1>
</div>
<div>
    <label for="task">Task : </label>
    <input id="task" placeholder="Enter Task" v-model="task" />
</div>
<button @click="addTodo(task)">Add Todo</button>
<div>
    <h1>Task List</h1>
   <div v-for="t,i in todos">
    
    <input type="text" :placeholder="t"  />
    <button @click="del(t,i)">Delete</button>

   </div>
</div>
</template>
<style scoped>


</style>