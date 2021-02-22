<template>
  <div id="title">
        <h1 id="title-text">TODO LIST</h1>
        <img id="img-title" alt="Vue logo" src="../assets/logo.png">
  </div>
</template>

<script>

export default {
  name: 'Title'
}

</script>

<style scoped>
      #title{
            display: flex;
            justify-content: center;
            align-items: center;
            margin: 50px 0px;
      }

      #title-text{
            font-size: 50px;
            margin: 0px 50px;
      }

      #img-title{
            height: 50px;
      }
</style>
