<template>
  <div class="min-h-screen flex flex-col justify-center items-center">
    <Header />
    <Main>
      <h4 class="text-center" v-if="todos.length==0">Enter an task to get the list started!</h4>
      <section class="space-y-4" v-if="pendingTodos.length>0">
        <h3 class="text-3xl text-green-800">Pending Items : {{pendingTodos.length}}</h3>
        <ul class="space-y-4">
          <li v-for="todo in pendingTodos" :key="todo.id" 
          class="bg-white rounded-xl text-2xl py-2 px-4 font-light text-center hover:text-white hover:bg-green-800 transition transform ease-in-out hover:scale-110 duration-500 cursor-pointer" 
          @click="changeStatus(todo.id)"
          >
          {{todo.text}}
          </li>
        </ul>
      </section>
      <section class="space-y-4" v-if="completedTodos.length>0">
        <h3 class="text-3xl text-red-800">Completed Items : {{completedTodos.length}}</h3>
        <ul class="space-y-4">
          <li v-for="todo in completedTodos" :key="todo.id" 
          class="bg-white rounded-xl text-2xl py-2 px-4 font-light text-center hover:text-white hover:bg-red-800 transition transform ease-in-out hover:scale-110 duration-500 cursor-pointer"
          @click="changeStatus(todo.id)"
          >
          {{todo.text}}
          </li>
        </ul>
      </section>
    </Main>
  </div>
</template>

<script setup>
import Header from './components/Header.vue'
import Main from './components/Main.vue'
import {pendingTodos, completedTodos, changeStatus, todos} from './helpers/useTodos.js'
</script>
