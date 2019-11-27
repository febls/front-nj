<template>
<div>

<v-container class="top-base-register">
<div>
    <div class="login">
     <a href="/"><p>voltar</p></a>
    </div>

    <center>
        <form action ="/minha-area" style="width: 50%;">
        <h1 class="section-title-login">Meus Dados</h1> 
        <br>
        <v-text-field class="label-form" v-model="nome" :error-messages="emailErrors" label="Nome"></v-text-field>
        <v-text-field class="label-form" v-model="email" :error-messages="emailErrors" label="E-mail"></v-text-field>
        <v-text-field class="label-form" v-model="telefone" :error-messages="emailErrors" label="Telefone"></v-text-field>
        <v-text-field class="label-form" v-model="endereco" :error-messages="emailErrors" label="Endereço"></v-text-field>
        <br>
        
        <v-row align="left" justify="space-around" style="margin-left: 286px; color: black !important;">
            <v-icon>fas fa-lock</v-icon>
        </v-row>

        <v-text-field type="password" class="label-form" v-model="senha" :error-messages="emailErrors" label="Senha"></v-text-field>
        <v-btn to="/minha-area" class="bt-editar-s">Voltar</v-btn>
        <v-btn class="bt-editar-p">Alterar dados</v-btn> 
        
        </form>
    </center>
  </div>
  </v-container>
</div>
</template>

<script>
     
    const routes = [
  { path: '/minha-area' }
];
</script>