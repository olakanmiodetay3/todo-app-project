<template>
    <div class="container">
    
        <h1 id="title">ToDo APPLICATION</h1>
      <div>
        <input
          type="text"
          class="input"
          value="todo"
          v-model="currentInput"
          />
          <button class="btn-add" @click="handleAddTodo">Add todo</button>
          </div>
        <div v-for="todo in todos" :key="todo">
            <input type="text" placeholder="inpute your todo" :value="todo" @input="handleUpdateEdit">
            <div>
            <button class=" btn-Edit" @click="handleEdit">Edit</button>
        <button class="btn-delete" @click="handleDelete(todo)">Delete</button>
     </div>
    
    </div>
            
        </div>
        
       
      
    </template>
    
    <script>
    export default {
      data() {
        return {
          todos: [],
          currentInput: "",
          editcurrentInput:"",
        };
      },
      methods: {
        handleAddTodo() {
    
            if(!this.currentInput) return
            this.todos.push(this.currentInput);
            this.currentInput=""
            
        },handleEdit(){
            this.currentInput= ""
        },handleDelete(todo){
            this.todos=this.todos.filter((item)=>item!=todo)
        },
    
        handleUpdateEdit(){
            editcurrentInput=currentInput
        }
      },
    };
    </script>
    
    <style scoped>
    .container{
        background-color: aquamarine;
        /* margin: 50px; */
        padding: 50px;
        border: 1px solid white;
        border-radius: 10px;
    };
    
    #title{
     border: 1px solid white;
     border-radius: 10px
    };
    .btn-add{
    padding: 4px;
    border: 1px solid black;
    border-radius: 3px;
    };
    
    .btn-Edit{
    padding: 4px;
    border: 1px solid black;
    border-radius: 3px;
    
    };
    .btn-delete{
    padding: 4px;
    border: 1px solid black;
    border-radius: 3px;
    }
    </style>
    