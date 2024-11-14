<template>
    <div class="login-page">
      <h2>Login</h2>
      <form @submit.prevent="handleLogin">
        <div class="form-group">
          <label for="username">Username</label>
          <input
            v-model="username"
            type="text"
            id="username"
            placeholder="Enter your username"
            required
          />
        </div>
        <div class="form-group">
          <label for="password">Password</label>
          <input
            v-model="password"
            type="password"
            id="password"
            placeholder="Enter your password"
            required
          />
        </div>
        <button type="submit">Login</button>
      </form>
      <p v-if="errorMessage" class="error">{{ errorMessage }}</p>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const username = ref('');
  const password = ref('');
  const errorMessage = ref('');
  
  function handleLogin() {
    // Basic validation or API call can go here
    if (username.value && password.value) {
      // Example of where you'd send the login info to an API
      console.log('Logging in with', username.value, password.value);
  
      // Reset the error message if there was one
      errorMessage.value = '';
  
      // Simulate a login success or failure
      if (username.value === 'admin' && password.value === 'password') {
        alert('Login successful!');
        // You can navigate or change state here as needed
      } else {
        errorMessage.value = 'Invalid username or password';
      }
    } else {
      errorMessage.value = 'Please fill out all fields';
    }
  }
  </script>
  
  <style scoped>
  .login-page {
    max-width: 400px;
    margin: auto;
    padding: 20px;
    border: 1px solid #ddd;
    border-radius: 8px;
  }
  .form-group {
    margin-bottom: 15px;
  }
  label {
    display: block;
    margin-bottom: 5px;
  }
  input {
    width: 100%;
    padding: 8px;
    box-sizing: border-box;
  }
  button {
    width: 100%;
    padding: 10px;
    background-color: #4CAF50;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
  }
  button:hover {
    background-color: #45a049;
  }
  .error {
    color: red;
    margin-top: 10px;
  }
  </style>
  