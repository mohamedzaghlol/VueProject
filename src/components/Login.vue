<template>
    <div>
      <h2>Login</h2>
      <form @submit.prevent="login">
        <label for="email">Email:</label>
        <input type="email" id="email" v-model="user.email" required>
        <label for="password">Password:</label>
        <input type="password" id="password" v-model="user.password" required>
        <button type="submit">Login</button>
      </form>
    </div>
  </template>
  
  <script>
  import axios from 'axios';
  
  export default {
    data() {
      return {
        user: {
          email: '',
          password: ''
        }
      };
    },
    methods: {
      login() {
        axios.post('/api/auth/login', this.user)
          .then(response => {
            // Handle success
            const token = response.data.token;
            // Store the token in local storage or a cookie
            // Redirect to the desired page
          })
          .catch(error => {
            // Handle error
          });
      }
    }
  };
  </script>