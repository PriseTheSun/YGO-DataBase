<template>
  <div class="text-center">
    <v-pagination v-model="page" :length="len" @input="changeIndex"
    :total-visible="10"
    ></v-pagination>
  </div>
</template>

<script>
export default {  

  data() {
    return {
      page: 1
    };
  },
  props:{
    total:Number,
    len:Number,
    changeIndex: Function
  }
  
}
</script>
