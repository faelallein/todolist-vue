<template>
      <div id="task">
            <h2>Nome: {{ data.name }}</h2>
            <h2>Descri&ccedil;&atilde;o: {{ data.description }}</h2>
      </div>
</template>


<script>
export default {
      name: "Task",
      props: { data : Object }     
}
</script>

<style scoped>
      #task{
            min-height: 130px;
            min-width: 95%;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: flex-start;
            padding: 0px 10px;
            margin: 10px 0px;
            border: solid;
      }
</style>