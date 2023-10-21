<template>
  <div id="app">
    <h1>{{ message }}</h1>
  </div>
</template>

<script>
import axios from "axios";


export default {
  data() {
    return {
      message: ""
    };
  },
  mounted() {
    axios.get("http://localhost:5000/api/message")
      .then(response => {
        this.message = response.data.message;
      })
      .catch(error => {
        console.error("There was an error!", error);
      });
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
