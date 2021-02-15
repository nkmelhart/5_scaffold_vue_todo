<template>
  <div class="min-h-screen flex flex-col justify-center items-center">
    <Header />
    <Main>
      <h4 class="text-center" v-if="todos.length==0">Enter an task to get the list started!</h4>
      <ListTodos color="green" title="Pending Items" :todos="pendingTodos"/>
      <ListTodos color="red" title="Completed Items" :todos="completedTodos"/>
    </Main>
  </div>
</template>

<script setup>
import Header from './components/Header.vue'
import Main from './components/Main.vue'
import ListTodos from './components/ListTodos.vue'
import {pendingTodos, completedTodos, changeStatus, todos} from './helpers/useTodos.js'
</script>
