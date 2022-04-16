<template>
<!--ApiDatabase-->
    <div>
      <div v-for="card in cards" :key=card.id>
          <v-img :src="card.card_images[0].image_url" alt=""/>
      </div>
    </div>   
</template>

<script>
export default {

    }; 
</script>

