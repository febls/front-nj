<template>
<div class="index-container">

  <div id="entrada">
    <v-container>
      <v-layout align-center fill-height row wrap>
        
        <v-flex flex md7 xs12 offset-xs1>
          <img src="/images/nice-logo.png" width="120px" alt="logo nice job">
          <h1 style="font-size:40px">A união faz a força, a Job une.</h1><br>
          <v-btn to="/login" class="bt-home">Contratar um serviço!</v-btn>
         <v-btn to="/login" class="bt-home-2">Quero trabalhar com a Job!</v-btn>
        </v-flex>
        
        <v-flex md4 xs12>
          <img src="/images/iphone.png" class="img-home" alt="utimos servicos">
        </v-flex>
      
      </v-layout>
    </v-container>
  </div>

  <div id="servicos" style="background-color: #FDF7FA;">
    <v-container>
      <h2 class="section-title">Deixe suas tarefas com quem entende, <br>selecione uma das categoria </h2>
      <br>
      <v-layout row wrap>
                    <v-flex md4 xs6>
                        <v-btn  to="/solicitar-pedido" class="btn-outlined" style="margin-left: -30px;">Limpeza</v-btn>
                    </v-flex>
                    <v-flex md4 xs6>
                        <v-btn to="/solicitar-pedido" style="margin-left: -17px;" class="btn-outlined" >Pintura</v-btn>
                    </v-flex>
                    <v-flex md4 xs6>
                        <v-btn to="/solicitar-pedido" style="margin-left: 0px;"  class="btn-outlined">Encanamento</v-btn>
                    </v-flex>
                    <v-flex md4 xs6>
                        <v-btn to="/solicitar-pedido" class="btn-outlined" style="margin-left: -30px;">Eletricista</v-btn>
                    </v-flex>
                    <v-flex md4 xs6>
                        <v-btn to="/solicitar-pedido" style="margin-left: -17px;"  class="btn-outlined">Jardinagem</v-btn>
                    </v-flex>
                    <v-flex md4 xs6>
                        <v-btn to="/solicitar-pedido"   style="margin-left: 0px;"  class="btn-outlined">Reparos</v-btn>
                    </v-flex>
                </v-layout>
                <br><br>
                <center><p style="font-size: 20px; font-weight: 600;">Não encontrou o que procura? Fale com a gente!</p></center>
    </v-container>
   
  </div>
   <div id="linkC"></div>
  

  <div id="comoFunciona">
    <v-container>
    <h2 class="section-comoFunciona">Descomplicamos o seu dia, veja como é fácil!</h2>
      
      <v-layout row wrap>
          <v-flex xs4 px-0>
            <img src="/images/entrar.png" alt="">
          </v-flex>
          
          <v-flex md4 px-0>
            <center><img src="/images/find.png" alt=""></center>
          </v-flex>
        
        <v-flex md1  offset-xs3>
          <img src="/images/choice.png" alt="">
        </v-flex>
      </v-layout>

      <div class="index-fluxo">
        <img src="/images/fase.png" style="width: 1190px; margin-left:11px;" alt="">
      </div>
      <br>
        <div class="index-cf"> 
        <div class="cf-one">Cadastre-se <br>ou faça seu login</div>
        <div class="cf-two">Encontre o serviço<br> que esta precisando</div>
        <div class="cf-three">Escolha o profissional,<br> e feche o serviço com ele!</div>
      </div>
      
    </v-container>
  </div>

    <div id="action">
            <v-container>
                <h2 class="section-call">Oferece algum tipo de serviço? Entre para a Nice Job!  </h2>
                <v-flex md12 xs12>
                <center><v-btn to="/cadastro-fornecedor" class="btn-action">Quero trabalhar com a Nice Job!</v-btn></center>
                 </v-flex>
                <template>
                    <v-flex md12 xs12>
                        
                    </v-flex>
                </template>

            </v-container>
        </div>
          
</div>
</template>

<script>
 

const routes = [
  { path: '/login' }
  ];
</script>