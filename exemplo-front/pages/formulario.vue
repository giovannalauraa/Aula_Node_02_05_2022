<template>
  <div class="container">
      <h3>Insira seus dados</h3>
      <form @submit.prevent="digaOla">
          <span ref="nome">Nome: </span>
          <input id="nome" v-model="form.nome" type="text" /> <br><br>
          <span ref="email"> Email: </span>
          <input id="email" v-model="form.email" type="email"/> <br><br>
          <button type="submit">Ok</button>
      </form>

      <div v-show="form.nome">
          <h4 v-if = "form.nome && form.email">
              Seus dados já podem ser enviados!
            </h4>
              <span v-else style="color: red;">Dados incompletos!</span>
      </div>
  </div>
</template>

<script>
export default {
    data: function(){
        return{
            form: {
                nome: '',
                email: '',
            },
        }
    },
    methods: {
        digaOla: function (){
            alert(JSON.stringfy(this.form))
        },
    },

}
</script>

<style scoped>
.container{
    margin: 20px;
}

</style>