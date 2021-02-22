<template>
      <form >
            <label for="name">Nome da Tarefa</label>
            <input type="text" name="name" id="" class="input-text" v-model="nameField">
            <label for="description">Descri&ccedil;&atilde;o</label>
            <input type="text" name="description" id="" class="input-text" v-model="descriptionField">
            <br/>
            <button type="button" class="input-btn" @click="addTask">Cadastrar</button>
      </form>
</template>

<script>
export default {
      name : "Form",
      data(){
            return {
                  nameField : "",
                  descriptionField : ""
            }
      },
      methods : {
            addTask : function() {
                  if(this.nameField == "" || this.descriptionField == ""){
                        alert("Preencha os Campos")
                  } else {
                        this.arrayTasks.push({
                              name : this.nameField,
                              description: this.descriptionField 
                        })

                        var myHeaders = new Headers();
                        myHeaders.append("Content-Type", "application/json");

                        var raw = JSON.stringify({"name": this.nameField, "description":this.descriptionField});

                        var requestOptions = {
                        method: 'POST',
                        headers: myHeaders,
                        body: raw,
                        redirect: 'follow'
                        };

                        fetch("http://localhost:8080/api/tasks", requestOptions)
                  }                  
            }
      },
      props: { arrayTasks : Array }
}
</script>

<style scoped>
      form{
            height: 200px;
            width: 80%;
            padding: 10px 0px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            align-items: center;
      }
      label{
            font-size: 25px;
      }
      .input-text{
            height: 25px;
            width: 80%;
      }
      .input-btn{
            width: 50%;
            height: 40px;
            font-size: 20px;
            color: #fff;
            background-color: #0d8dde;
            border: none;
            border-radius: 8px;
      }

      .input-btn:hover{
            background-color: #70c1f3;
      }

      .input-btn:focus{
            outline: none;
      }     
</style>