<template>
      <div id="tasks">
            <h1 v-if="arrayTasks.length == 0">Sem Tarefas</h1>
            <div v-for="(task, index) in arrayTasks" :key="index" id="div-for">
                  <Task :data="task"/>
            </div>
      </div>
</template>

<script>
import Task from './Task'

export default {
      name: "Tasks",
      components: { Task },
      props: { arrayTasks : Array }
}
</script>

<style scoped>
      #tasks{
            border: solid;
            width: 80%;
            min-height: 100px;
            display: flex;
            flex-direction: column;
            align-items: center;
      }
      #div-for{ width: 95%;}
</style>