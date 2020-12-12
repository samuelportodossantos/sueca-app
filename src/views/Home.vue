<template>
  <div class="home">

    <div class="board-cards">

    </div>

    <div class="selected-card">
      <div @click="resetCard()">
        <card  v-show="selectedCard.path !== ''" :path="selectedCard.path" />
      </div>
    </div>

    <div class="game-board">
      <div class="hand-card-board">
        <div v-for="(card, key) in hand" :key="key" @click="selectCard(card)">
          <card :path="card.path" />
        </div>
      </div>
      <hr />
      <button @click="generateHand()">Randomizar cartas</button>
    </div>

  </div>
</template>

<script>
import Card from "../components/Card.vue";
import cardsService from "../helpers/cards.js";

export default {
  name: "Home",
  components: {
    Card,
  },
  data: () => {
    return {
      hand: [],
      selectedCard: {
        label: "",
        path: "",
        value: "  ",
      },
    };
  },
  mounted() {
    this.generateHand();
  },
  computed: {
    cards() {
      return cardsService.getAll();
    },
  },
  methods: {
    generateHand() {
      this.hand = cardsService.getRandomCards(this.cards, 9);
    },
    selectCard(card) {
      this.selectedCard = card;
    },
    resetCard() {
      this.selectedCard = {
        label: "",
        path: "",
        value: "  ",
      }
    }
  },
};
</script>

<style scoped>
.game-board {
  display: flex;
  justify-content: center;
  flex-direction: column;
}

.hand-card-board {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
}
</style>
