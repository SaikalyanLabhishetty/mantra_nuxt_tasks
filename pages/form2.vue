<template>
    <div>
      <h2>Login</h2>
      <div class="form">
        <form @submit.prevent="login">
          <label for="loginUsername">Username</label>
          <input id="loginUsername" v-model="loginUsername"><br/>
          <label for="loginPassword">Password</label>
          <input id="loginPassword" type="password" v-model="loginPassword"><br/>
          <button type="submit">Login</button>
        </form>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue'
  import { userStore } from '@/store'
  
  const loginUsername = ref(userStore.username)
  const loginPassword = ref(userStore.password)
  
  function login() {
  
    console.log('Logging in...')
    console.log('Username:', loginUsername.value)
    console.log('Password:', loginPassword.value)
  
    loginUsername.value = ''
    loginPassword.value = ''
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
  