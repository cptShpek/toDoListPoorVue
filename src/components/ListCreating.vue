<template>
  <div id="creating">
    <div>
      <h2>Create your todo list here!</h2>
      <input type="text" v-model="inputValue"><button @click="createTodo( inputValue )">Create!</button>
    </div>
    <div>
      <h2>Your Todo list!</h2>
      <ul>
        <li v-for="(todo, index) in todoList" :key="todo">
          {{todo}} 
          <button @click="deleteItem( index )">Delete!</button>
          <button @click="addDoneTodo( index )">Done!</button>
        </li>
      </ul>
    </div>
    <div>
      <h2>Your Done List Here!</h2>
      <ul>
        <li v-for="done in doneList" :key="done">{{done}}</li>
      </ul>
    </div>
  </div>
</template>

<script>

  export default {

    name: 'ListCreating',

    data() { return {

        inputValue: '',
        todoList: [],
        doneList: [],

      }
    },

    methods: {

      createTodo: function ( el ){

        this.todoList.push( el );
        return;

      },

      deleteItem: function ( index ){

        this.todoList.splice( index, 1 );
        return;

      },

      addDoneTodo: function ( index ) {

        this.doneList.push( this.todoList[index] );
        this.deleteItem( index );
        return;

      }

    },

  }
</script>

<style scoped>
</style>
