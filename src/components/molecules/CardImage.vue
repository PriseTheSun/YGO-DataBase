<template>
    <v-card
      class="mx-auto"
      max-width="344"
    >
     <v-img
     :src='card.card_images[0].image_url'
     />

      <v-card-title>
        {{card.name}}
      </v-card-title>
  
      <v-card-subtitle>
        {{card.type}}
      </v-card-subtitle>
  
      <v-card-actions>
        <v-btn
          class="mt-5"
          color="orange lighten-2"
          text
        >
         <shere-button
         
         />
        </v-btn>
  
        <v-spacer></v-spacer>
  
        <v-btn
          icon
          @click="show = !show"
        >
          <v-icon>{{ show ? 'mdi-chevron-up' : 'mdi-chevron-down' }}</v-icon>
        </v-btn>
      </v-card-actions>
  
      <v-expand-transition>
        <div v-show="show">
          <v-divider></v-divider>
  
          <v-card-text>
            {{card.desc}}
          </v-card-text>
        </div>
      </v-expand-transition>
    </v-card>
</template>

<script>
import ShereButton from '@/components/atom/ShereButton.vue'

export default {
  data: () => ({
    show: false,
  }),
  mounted(){
    console.log("CARD: ", this.card);
  },
  components:{
      ShereButton
  },
  props:{
      card:Object
  }
}
</script>