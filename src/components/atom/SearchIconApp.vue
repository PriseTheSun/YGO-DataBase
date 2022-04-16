<template>
    <div class="d-flex">

       <v-btn
       color="indigo lighten-5"
       icon
       >
       <v-icon>
          mdi-magnify
        </v-icon>
      </v-btn>

      <v-text-field
      @input="search" 
      label="Encontre sua Carta"
      color="indigo lighten-5"
      
      >
      </v-text-field>
    </div>
    

</template>

<script>

  export default {
   name: 'SearchIconApp',
   props:{
     search: Function,
   },
   data(){
     return{
       
     }
   },
  methods:{
    tmp:function(input){
        console.log(input);
      },
  }
  }
</script>

<style scoped>
.auto-complete{
  max-width: 300px;
}
</style>