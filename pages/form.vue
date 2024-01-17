<template>
  <div>
    <h2 class="text-center">Student Data</h2>
    <div class="form">
      <form @submit.prevent="register" class="flex flex-col">
        <label for="username">Username</label>
        <input id="username" v-model="username" class="h-12 border mb-4"><br/>
        <label for="password">Password</label>
        <input id="password" type="password" v-model="password" class="h-12 border mb-4"><br/>
        <button type="submit" class="bg-blue-500 h-12 text-white font-base cursor-pointer">Register</button>
      </form>
    </div>
  </div>
</template>
  
  <script setup>
  import { ref } from 'vue'
  import { userStore } from '@/store'
  
  const username = ref('')
  const password = ref('')
  
  function register() {
    userStore.username = username.value
    userStore.password = password.value
  
    username.value = ''
    password.value = ''
  }
  </script>
  
 