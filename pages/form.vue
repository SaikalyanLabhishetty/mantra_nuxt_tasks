<template>
    <div>
      <h2>Student Data</h2>
      <div class="form">
        <form @submit.prevent="register">
          <label for="username">Username</label>
          <input id="username" v-model="username"><br/>
          <label for="password">Password</label>
          <input id="password" type="password" v-model="password"><br/>
          <button type="submit">Register</button>
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
  
 
<style scoped>
form {
  display: flex;
  flex-direction: column;
}
input {
  height: 30px;
}
.form button {
  background-color: rgb(44, 100, 165);
  height: 50px;
  border: none;
  font-size: 18px;
  cursor: pointer;
}
h2 {
  text-align: center;
}
</style>