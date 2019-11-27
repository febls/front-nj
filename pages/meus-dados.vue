<template>
<div>

<v-container class="top-base-register">
<div>
    <div class="login">
     <a href="/"><p>voltar</p></a>
    </div>

    <center>
        <form @submit="alterarDados" style="width: 50%;">
          <h1 class="section-title-login">Meus Dados</h1><br>

          <v-text-field id="nome" class="label-form" :value="nome" placeholder="Nome"></v-text-field>
          <v-text-field id="telefone" class="label-form" :error-messages="emailErrors" placeholder="Telefone"></v-text-field>
          <v-text-field id="endereco" class="label-form" :error-messages="emailErrors" placeholder="Endereço"></v-text-field>
          <v-text-field id="email" class="label-form" :error-messages="emailErrors" placeholder="E-mail"></v-text-field>
          <v-text-field id="senha" type="password" class="label-form" :error-messages="emailErrors" placeholder="Senha"></v-text-field>
         
          <v-btn @click="preencherCampos" class="bt-editar-s">Dados</v-btn>
          <v-btn type="submit" class="bt-editar-p">Alterar dados</v-btn> 
        </form>
    </center>
  </div>
  </v-container>
</div>
</template>

<script>
  const axios = require('axios');

  export default {
    data(){
      return{
        nome: '',
        email: '',
        telefone: '',
        endereco: '',
        senha: ''
      }
    },

    mounted(){
      sessionStorage.removeItem("pedidos");
    },

    methods: {
      preencherCampos(){
        axios.get('http://api-nicejobs.herokuapp.com/getUser/'+sessionStorage.getItem("id"))
        .then(dados => {
          document.getElementById("nome").value = dados.data.nome;
          document.getElementById("telefone").value = dados.data.telefone;
          document.getElementById("endereco").value = dados.data.endereco;
          document.getElementById("email").value = dados.data.email;
          document.getElementById("senha").value = dados.data.senha;
        })
        .catch(error => {
          console.log(error);
        })
      },

      alterarDados(e){
        e.preventDefault();

        const id = sessionStorage.getItem("id");
        const nome = document.getElementById("nome").value;
        const telefone = document.getElementById("telefone").value;
        const endereco = document.getElementById("endereco").value;
        const email = document.getElementById("email").value;
        const senha = document.getElementById("senha").value;

        const parametros = new URLSearchParams();
        parametros.append("id", id);
        parametros.append("nome", nome);
        parametros.append("email", email);
        parametros.append("telefone", telefone);
        parametros.append("endereco", endereco);
        parametros.append("senha", senha);
        axios.put('http://api-nicejobs.herokuapp.com/updateUser', parametros)
        .then(function (response) {
            if(response.status == 200){
                window.location.href = '/minha-area';
            }else if(response.status == 201){
                alert("");
                window.location.href = '/minha-area';
            }
        })
        .catch(function (error) {
            console.log(error);
        })
      }
    }
  }
     
  const routes = [
    { path: '/minha-area' }
  ];
</script>