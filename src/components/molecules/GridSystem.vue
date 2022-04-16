<template>
  <!--GridSystem-->
  <v-container class="grey lighten-5">
    <SetPgntnApp
      v-if="cards.length > 0"
      :len="total / perPage"
      :total="total"
      :changeIndex="changeIndex"
    />
    <div class="my-10"></div>
    <v-row no-gutters>
      <v-col
        v-for="card in cards"
        :key="card.id"
        cols="12"
        sm="4"
        class="mb-10"
      >
        <card-image :card="card" />
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import CardImage from "@/components/molecules/CardImage.vue";
import SetPgntnApp from "@/components/molecules/SetPgntnApp";
export default {
  props: {
    search: String,
  },
  watch: {
    search: function () {
      this.searchCards();
    },
  },
  data() {
    return {
      originalCards: [],
      cards: [],
      cardsSearched: [],
      total: 0,
      len: 10,
      perPage: 10,
      currentIdx: 1,
    };
  },
  components: {
    CardImage,
    SetPgntnApp,
  },
  methods: {
    searchCards: function () {
      const tmp = this.originalCards.filter((it) => {
        return (
          it.name
            .toLowerCase()
            .trim()
            .indexOf((this.search || "").toLowerCase().trim()) > -1
        );
      });
      this.cardsSearched = [...tmp];
      this.total = this.cardsSearched.length;
      console.log("LEN:" + this.total);
      this.listPagination();
    },
    listPagination: function () {
      this.total = this.cardsSearched.length;
      this.cards = this.cardsSearched.slice(
        (this.currentIdx - 1) * this.perPage,
        this.perPage * this.currentIdx
      );
    },
    changeIndex: function (idx) {
      this.currentIdx = idx;
      this.listPagination();
      console.log(this.cards);
    },
  },
  mounted() {
    fetch("https://db.ygoprodeck.com/api/v7/cardinfo.php?language=pt")
      .then((res) => res.json())
      .then((res) => {
        this.originalCards = res.data;
        this.cardsSearched = res.data;
        this.listPagination();
        //this.total = this.originalCards.length
      });
  },
};
</script>
