<template>
<div>
    <v-container class="page-header p-t-70">
    <h2 class="internal-title">Veja todos os prestadores disponiveis</h2> 
    </v-container>

    <v-container >
        <div class="l-first">
            <div class="one-p">
                <div class="one-left">
                    <img src="/images/placeholder-p.png" width="130px" alt="">
                </div>
                <div class="one-right">
                   <ul class="l-ul">
                       <li>User 01</li>
                       <li>Rua 12346</li>
                       <li>Eletricista, Reparos</li>
                   </ul>
                    <v-btn @click.stop="dialog = true" class="p-perfil">Escolher</v-btn>
                    <v-btn class="p-escolher">Ver Perfil</v-btn>
                    <v-btn class="p-escolher">Chat</v-btn>
                </div>
            </div>

            <div class="two-l">
                 <div class="two-left">
                    <img src="/images/placeholder-p.png" width="130px" alt="">
                </div>
                <div class="two-right">
                     <ul class="l-ul">
                       <li>User 01</li>
                       <li>Rua 12346</li>
                       <li>Eletricista, Reparos</li>
                   </ul>
                    <v-btn @click.stop="dialog = true" class="p-perfil">Escolher</v-btn>
                    <v-btn class="p-escolher">Ver Perfil</v-btn>
                    <v-btn class="p-escolher">Chat</v-btn>
                    
                </div>
            </div>  
        </div>
        <br>
         <div class="l-first">
            <div class="one-p">
                <div class="one-left">
                    <img src="/images/placeholder-p.png" width="130px" alt="">
                </div>
                <div class="one-right">
                   <ul class="l-ul">
                       <li>User 01</li>
                       <li>Rua 12346</li>
                       <li>Eletricista, Reparos</li>
                   </ul>
                    <v-btn @click.stop="dialog = true" class="p-perfil">Escolher</v-btn>
                    <v-btn class="p-escolher">Ver Perfil</v-btn>
                    <v-btn class="p-escolher">Chat</v-btn>
                </div>
            </div>

            <div class="two-l">
                 <div class="two-left">
                    <img src="/images/placeholder-p.png" width="130px" alt="">
                </div>
                <div class="two-right">
                    <ul class="l-ul">
                       <li>User 01</li>
                       <li>Rua 12346</li>
                       <li>Eletricista, Reparos</li>
                   </ul>
                    <v-btn @click.stop="dialog = true" class="p-perfil">Escolher</v-btn>
                    <v-btn class="p-escolher">Ver Perfil</v-btn>
                    <v-btn class="p-escolher">Chat</v-btn>
                    
                </div>
            </div>  
        </div>
        <div class="l-forncedor">
            <v-btn to="/" class="bt-lc">Cancelar</v-btn>
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
        dialog: false
      }
    }
  }
  </script>