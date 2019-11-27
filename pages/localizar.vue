<template>
<div>
    <v-container class="page-header p-t-70">
    <h2 class="internal-title">Escolha o profissional ideal!</h2> 
    </v-container>

    <v-container >
        <div class="p-first">
            <div class="one-p">
                <div class="one-left">
                    <img src="/images/charles.png" width="130px" alt="">
                </div>
                <div class="one-right">
                  <p>{{ nomeUm }}</p>
                  <p>{{ emailUm }}</p>
                  <p>{{ ruaUm }}</p>

                  <v-btn @click.stop="dialog = true" class="p-perfil">Escolher</v-btn>
                  <v-btn class="p-escolher">Ver Perfil</v-btn>
                  <v-btn class="p-escolher">Chat</v-btn>
                </div>
            </div>

            <div class="two-p">
                 <div class="two-left">
                    <img src="/images/felipe.jpg" width="130px" alt="">
                </div>
                <div class="two-right">
                    <p>{{ nomeDois }}</p>
                    <p>{{ emailDois }}</p>
                    <p>{{ ruaDois }}</p>
                    <v-btn @click.stop="dialog = true" class="p-perfil">Escolher</v-btn>
                    <v-btn class="p-escolher">Ver Perfil</v-btn>
                    <v-btn class="p-escolher">Chat</v-btn>
                    
                </div>
            </div>
        </div>
        <div class="l-forncedor">
            <v-btn class="bt-lc">Ver todos fornecedores</v-btn>
        </div>
        
    </v-container>

     <v-dialog
      v-model="dialog"
      max-width="600"
    >
      <v-card>
        <v-card-title class="headline modal" >Confirma a contratação do fornecedor?</v-card-title>

        <v-card-text>
          Caso tenha certeza da escolha do fornecedor, confirme no botão <strong>'Concluir'</strong>.

        Caso queira cancelar, clique no bptão <strong>'fechar'</strong>
          
        </v-card-text>

        <v-card-actions>
          <v-spacer></v-spacer>

          <v-btn
            class="bt-modal-close"
            flat="flat"
            @click="dialog = false"
          >
            Fechar
          </v-btn>

          <v-btn
            class="bt-modal"
            flat="flat"
            to="/minha-area"
          >
            Concluir
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
</div>
</template>

<script>
  export default {
    data () {
      return {
        dialog: false,
        nomeUm: '',
        nomeDois: '',
        emailUm: '',
        emailDois: '',
        ruaUm: '',
        ruaDois: ''
      }
    },

    mounted(){
      axios.get('http://api-nicejobs.herokuapp.com/getHired')
      .then(dados => {
          for(let i = 0; i < dados.data.length; i++){
              if(i == 0){
                  this.nomeUm = dados.data[i].nome;
                  this.emailUm = dados.data[i].email;
                  this.ruaUm = dados.data[i].endereco;
              }else{
                  this.nomeDois = dados.data[i].nome;
                  this.emailDois = dados.data[i].email;
                  this.ruaDois = dados.data[i].endereco;
              }
          }
      })
      .catch(error =>{
          console.log("Houve um erro: ", error);
      })
    }
  }
  </script>