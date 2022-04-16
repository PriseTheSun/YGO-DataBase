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