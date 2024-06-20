<template>
    <div>
      <h2>Update Person</h2>
      <form @submit.prevent="updatePerson">
        <label for="name">Name:</label>
        <input type="text" id="name" v-model="person.name" required>
        <label for="email">Email:</label>
        <input type="email" id="email" v-model="person.email" required>
        <label for="phone">Phone:</label>
        <input type="tel" id="phone" v-model="person.phone" required>
        <label for="grad">Grad:</label>
        <select id="grad" v-model="person.grad" required>
          <option value="good">Good</option>
          <option value="very good">Very Good</option>
          <option value="excellent">Excellent</option>
        </select>
        <button type="submit">Update</button>
      </form>
    </div>
  </template>
  
  <script>
  import axios from 'axios';
  
  export default {
    data() {
      return {
        person: {
          name: '',
          email: '',
          phone: '',
          grad: ''
        }
      };
    },
    mounted() {
      axios.get('/api/persons/{personId}')
        .then(response => {
          this.person = response.data;
        })
        .catch(error => {
          // Handle error
          alert(error)

        });
    },
    methods: {
      updatePerson() {
        axios.put('/api/persons/{personId}', this.person)
          .then(response => {
            // Handle success
            alert(response)
          })
          .catch(error => {
            // Handle error
            alert(error)

          });
      }
    }
  };
  </script>