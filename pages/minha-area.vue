<template>
<div>
    <v-container class="page-header p-t-70">
    <h2 class="internal-title">Olá, {{ nome }}</h2> 
    </v-container>
<br>
<v-container class="c-minha-area">
  <v-layout row wrap>
    <v-flex md4 xs12>
      <div class="m-left">
        <div class="m-dados">
          <v-btn class="minha-area-btn">Meus Dados</v-btn>
        </div>
        <div class="m-sair">
          <v-btn @click="logout" class="minha-area-btn">Sair</v-btn>
        </div>
      </div>
    </v-flex>
                  
    <v-flex md1 xs12>
      <div class="vl"></div>
    </v-flex>

    <v-flex md7 xs12 class="r-area">                  
      <h2 class="m-h-area">Meus Pedidos</h2>
      
      <v-tabs left color="cyan" light icons-and-text>
      
      <v-tabs-slider color="#451F55"></v-tabs-slider>
      
      <v-tab @click="pedidos">Ativos</v-tab>
      <v-tab>Finalizados</v-tab>

      <v-tab-item>
        <v-card flat>
          <v-card-text>
            <div id="box" class="m-area-s" v-for="pedidos in pedidosAtivos" :key="pedidos">
              <ul class="m-area-ul">
                  <li>Serviço: {{ pedidos.servico }}</li>
                  <li>Data: {{ pedidos.data }}</li>
                  <li>Contratante: {{ pedidos.nome }}</li>
              </ul>
              <v-btn to="/editar-pedido" class="p-escolher">Editar</v-btn>
              <v-btn class="p-escolher">Chat</v-btn>
            </div> 
          </v-card-text>
        </v-card>                           
      </v-tab-item>

      <v-tab-item>
        <v-card flat>
          <v-card-text>Finalizados</v-card-text>
        </v-card>                           
      </v-tab-item>
      </v-tabs>
      <br> 
      <v-btn to="/solicitar-pedido" class="bt-m-area">Publicar um job!</v-btn>       
    </v-flex>
  </v-layout>
</v-container>
</div>
</template>

<script>
 export default {
    data(){
      return{
        currentItem: 'tab-1',
        text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.',
        currentItem: 'tab-2',
        text: 'Lorem ipsum dolor sit amet',
        nome: '',
        pedidosAtivos: []
      }
    },
    mounted(){
      console.log("mounted");
      if(!sessionStorage.getItem("nome")){
        window.location.href = "/";
      }else{
        this.nome = sessionStorage.getItem("nome");
      }
    },
    methods: {
      logout(){
        sessionStorage.clear();
        window.location.href = "/";
      },

      pedidos(){
        if(!sessionStorage.getItem("pedidos")){
          axios.get('http://api-nicejobs.herokuapp.com/getOrder')
            .then(dados => {
              if(dados.status == 200){
                for(let i = 0; i < dados.data.length; i++){
                  if(dados.data[i].idContractor == sessionStorage.getItem("id")){
                    let dadosPedidos = {
                      servico: dados.data[i].servico,
                      data: dados.data[i].data,
                      nome: sessionStorage.getItem("nome")
                    }; 

                    this.pedidosAtivos.push(dadosPedidos);
                  }
                }

                console.log(this.pedidosAtivos);
                sessionStorage.setItem("pedidos", this.pedidosAtivos);
              }
            })
            .catch(error =>{
              console.log('Houve um erro: ', error);
            })
          }
        }
      }
    }
    const routes = [
    { path: '/solicitar-pedido' }
    ];
</script>

<style>
  .vl {
    border-left: 4px solid #451F55;
    height: 400px;
  }

  #box{
    margin-bottom: 5px;
  }
</style>