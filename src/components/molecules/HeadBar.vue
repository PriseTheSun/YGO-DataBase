<template>
<!--HeadBar-->
    <v-app-bar
      color="#153988"
      dense
    >
      <v-app-bar-nav-icon
      color="white"
      >

      </v-app-bar-nav-icon>

      <v-app-bar-title
      class="white--text"
      >
      YGO DATABASE
      </v-app-bar-title>
      <v-spacer></v-spacer>
      <SearchIconApp :search="search" />
    </v-app-bar>

</template>

<script>
import SearchIconApp from '@/components/atom/SearchIconApp'

export default {
 components:{
  SearchIconApp
 },
 props:{
   search:Function
 }
 
}
</script>
