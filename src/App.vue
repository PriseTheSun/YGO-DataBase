<template>
  <v-app>
    <HeadBar :search=tmp />
    <ParalaxHero />
    <GridSystem :search=mySearch />
    <SetFoot/>
  </v-app>
</template>

<script>
import HeadBar from "@/components/molecules/HeadBar";
import ParalaxHero from "@/components/molecules/ParalaxHero";
import GridSystem from "@/components/molecules/GridSystem";
import SetFoot from  '@/components/molecules/SetFoot.vue'

alert('Saudações usuário espero que esteja bem. Desenvolvi este projeto consumindo a api do site (https://db.ygoprodeck.com/api-guide/) a ideia principal era tornar o site mais pratico, sem que o usuario precisasse setar a lingua pt (sim português de PORTUGAL pois era a linguagem mais próxima do nosso querido português BR que a api me fornecia. Logo ao pesquisar sua carta certifique-se que a linguagem esta adequada a sua busca.) para então ter acessoa a suas cartas em sua lingua. Este projeto foi desenvolvido para fins de estudo totalmente do zero para aplicar os conhecimentos obtidos durante meus estudos de VUE.JS, JS e VUETFY e conforme for avançando novas atualizações serão implementadas aguarde!!!!! E Hora do Duelo')

export default {
  name: "App",

  components: {
    HeadBar,
    ParalaxHero,
    GridSystem,
    SetFoot
  },
  data(){
    return {
      mySearch: null,
    };
  },
  methods: {
    tmp: function(val){
      console.log(val);
      this.mySearch= val;
    },
  },
};
</script>
