<template>
  <div class="home">

    <div class="game-board">
      <div class="player-card-board">
        <card
          :spritePath="cards[0].imagePath"
        />
        <card
          :spritePath="cards[0].imagePath"
        />
        <card
          :spritePath="cards[0].imagePath"
        />
        <card
          :spritePath="cards[0].imagePath"
        />
      </div>
    </div>
    



  </div>
</template>

<script>
import Card from '../components/Card.vue';
import cards from '../helpers/cards.js'

console.log(cards);

export default {
  name: 'Home',
  components: {
    Card
  },
  data: () => {
    return {
      cards: cards
    }
  }
}
</script>

<style scoped>
  .gamee-board {
    display: flex;

  }

  .player-card-board {
    display: flex;
    flex-direction: row;
    justify-content: space-around;
    background: rebeccapurple;
  }

</style>
