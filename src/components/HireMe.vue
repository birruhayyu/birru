<template>
<v-card
    class="mx-auto"
    max-width="300"
  >
  <v-text-field
      label="Email"
    v-model="userData.email"></v-text-field>
    <v-text-field label="Message" v-model="userData.password"></v-text-field>
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

    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
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
