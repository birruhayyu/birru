<template>
  <v-card class="mx-auto" max-width="300">
    <v-text-field v-model="userData.email" label="Email"></v-text-field>
    <v-text-field v-model="userData.password" label="Message"></v-text-field>
    <v-btn @click="registerUser">Submit</v-btn>
  </v-card>
</template>

<script>
export default {
  name: 'HireMe',
  props: {
    msg: String
  },
  data() {
    return {
      userData: {
        email: '',
        password: ''
      }
    }
  },
  methods: {
    registerUser() {
      console.log('User Registered:', this.userData);
    }
  }
}
</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
