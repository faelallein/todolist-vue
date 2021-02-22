<template>
  <div id="app">
    <Title />
    <Form   :arrayTasks="arrayTasks" />
    <Tasks  :arrayTasks="arrayTasks" />
  </div>
</template>

<script>
import Title from "./components/Title";
import Form from "./components/Form";
import Tasks from "./components/Tasks";

export default {
  name: "App",
  components: { Title, Form, Tasks, },
  data() {
    return { arrayTasks: [] };
  },
  created: function () {
    var requestOptions = { method: "GET" };

    fetch("http://localhost:8080/api/tasks", requestOptions)
      .then((response) => response.json())
      .then((result) => this.arrayTasks = result )
      .catch((error) => console.log("error", error));
  }
};
</script>

<style>
#app {
    font-family: sans-serif;
    text-align: center;
    color: #2c3e50;
    display: flex;
    flex-direction: column;
    align-items: center;
}
</style>
