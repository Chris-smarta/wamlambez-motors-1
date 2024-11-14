<template>
    <div class="signup-page">
      <h2>Sign Up</h2>
      <form @submit.prevent="handleSignup">
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
          <label for="email">Email</label>
          <input
            v-model="email"
            type="email"
            id="email"
            placeholder="Enter your email"
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
        <button type="submit">Sign Up</button>
      </form>
      <p v-if="errorMessage" class="error">{{ errorMessage }}</p>
      <p v-if="successMessage" class="success">{{ successMessage }}</p>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const username = ref('');
  const email = ref('');
  const password = ref('');
  const errorMessage = ref('');
  const successMessage = ref('');
  
  function handleSignup() {
    if (!username.value || !email.value || !password.value) {
      errorMessage.value = 'Please fill out all fields.';
      successMessage.value = '';
      return;
    }
  
    // Simple email format check (you could use a more robust regex)
    const emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
    if (!emailPattern.test(email.value)) {
      errorMessage.value = 'Please enter a valid email address.';
      successMessage.value = '';
      return;
    }
  
    // Placeholder for signup logic (e.g., API call)
    console.log('Signing up with
  