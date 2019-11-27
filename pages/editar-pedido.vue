<template>
<div>
    <v-container class="page-header p-t-70">
    <h2 class="internal-title">Confira os dados do pedido</h2> 
    </v-container>

    <v-container >
        <v-layout align-center justify-center row fill-height>
    <div id="pedido">
        <form style="display: table-caption;">
        <v-select
        v-model="servico"
        v-validate="'required'"
        :items="items"
        label="Serviço"
        class="internal-form"
        data-vv-name="select"
        required
        ></v-select>
        
        <v-select
        v-model="local"
        v-validate="'required'"
        :items="items_2"
        label="Local"
        class="internal-form"
        data-vv-name="select"
        required
        ></v-select>

        <v-subheader class="pl-0">Áreas:</v-subheader>
        <br>
            <v-slider
            v-model="quantidadeAreas"
            :thumb-size="24"
            thumb-label="always"
            class="internal-form"
            ></v-slider>
            
            <div class="internal-text-box">
            <v-textarea  
            outline
            name="input-7-4"
            class="internal-form"
            label="Descrição.."
            
            ></v-textarea></div>
            <h2 class="internal-title">Endereço</h2> 
            <v-text-field 
                v-model="cep"
                class="internal-form"
                label="CEP"
                
            
            ></v-text-field>
            <v-text-field 
                v-model="endereco"
                class="internal-form"
                label="Endereço"
            ></v-text-field>

        <v-menu
            ref="menu"
            v-model="data"
            :close-on-content-click="false"
            :nudge-right="40"
            :return-value.sync="date"
            lazy
            transition="scale-transition"
            offset-y
            full-width
            min-width="30px"
        >
            <template v-slot:activator="{ on }">
            <v-text-field
                v-model="date"
                label="Data"
                prepend-icon=""
                readonly
                v-on="on"
                class="internal-form"
            ></v-text-field>
            </template>
            <v-date-picker v-model="date" no-title scrollable>
            <v-spacer></v-spacer>
            <v-btn flat color="primary" @click="menu = false">Cancel</v-btn>
            <v-btn flat color="primary" @click="$refs.menu.save(date)">OK</v-btn>
            </v-date-picker>
        </v-menu>
        <center>
        <v-btn to="/localizar" class="bt-editar-s">Alterar</v-btn>
        <v-btn to="/localizar" class="bt-editar-p">Excluir</v-btn> 
        </center>  
    </form>
</div>
</v-layout>
</v-container>


</div>
</template>
<script>
export default {
    data: () => ({
      items: ['Limpeza Residencial', 'Reparos', 'Eletricista'],
      items_2: ['Casa', 'Apartamento', 'Empresa'],
      date: new Date().toISOString().substr(0, 10),
      menu: false,
      modal: false,
      menu2: false,
      servico: '',
      local: '',
      quantidadeAreas: '',
      descricao: '',
      cep: '',
      endereco: '',
      data: ''
    }),

    mounted(){

    }
  }

const routes = [
  { path: '/localizar' }
  ];

</script>
