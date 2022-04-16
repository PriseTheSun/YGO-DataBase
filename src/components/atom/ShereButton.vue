<template>
      <v-speed-dial
        v-model="dialShare"
        absolute
        right
        bottom
        direction="right"
        open-on-hover
      >
        <template v-slot:activator>
          <v-btn fab bottom small color="primary">
            <v-icon v-if="dialShare">mdi-close</v-icon>
            <v-icon v-else>mdi-share-variant</v-icon>
          </v-btn>
        </template>

        <v-btn dark fab bottom color="blue" small :href="`https://www.facebook.com/sharer/sharer.php?u=${pageUrl}`" target="_blank">
          <v-icon>mdi-facebook</v-icon>
        </v-btn>

        <v-btn dark fab bottom color="green" small :href="`https://web.whatsapp.com/${pageUrl}`" target="_blank">
          <v-icon>mdi-whatsapp</v-icon>
        </v-btn>

        <v-btn dark fab bottom color="tertiary" small :href="`mailto:?subject=Awesomeness!&amp;body=Checkout this page!<a href='${pageUrl}'>${pageUrl}</a>`" target="_blank">
          <v-icon>mdi-email</v-icon>
        </v-btn>

      </v-speed-dial>
</template>

<script>
export default {
  methods: {},
  data() {
    return {
      dialShare: false,
    };
  },
}
</script>