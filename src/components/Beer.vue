<template>
  <div class="beer">
    <h2 class="beer__title">Proposed beer</h2>
    <div class="beer__section">
      <span><b>Brand:</b> {{ brand }}</span>
    </div>
    <div class="beer__section">
      <span><b>Name:</b> {{ name }}</span>
    </div>
    <div class="beer__section">
      <span><b>Style:</b> {{ style }}</span>
    </div>
    <div class="beer__section">
      <span><b>Hop:</b> {{ hop }}</span>
    </div>
    <div class="beer__section">
      <span><b>Yeast:</b> {{ yeast }}</span>
    </div>
    <div class="beer__section">
      <span><b>Malts:</b> {{ malts }}</span>
    </div>
    <div class="beer__section">
      <span><b>Ibu:</b> {{ ibu }}</span>
    </div>
    <div class="beer__section">
      <span><b>alcohol:</b> {{ alcohol }}</span>
    </div>
    <div class="beer__section">
      <span><b>Blg:</b> {{ blg }}</span>
    </div>
    <div class="beer__btns">
      <beer-button @click="fetchBeer" style="background-color: red" text="Dislike"/>
      <beer-button @click="likeBeer" style="background-color: green" text="Like"/>
    </div>
  </div>
</template>

<script>
import BeerButton from "./BeerButton";

export default {
  components: {
    BeerButton
  },
  props: {
    brand: {
      type: String,
      required: true
    },
    name: {
      type: String,
      required: true
    },
    style: {
      type: String,
      required: true
    },
    hop: {
      type: String,
      required: true
    },
    yeast: {
      type: String,
      required: true
    },
    malts: {
      type: String,
      required: true
    },
    ibu: {
      type: String,
      required: true
    },
    alcohol: {
      type: String,
      required: true
    },
    blg: {
      type: String,
      required: true
    },
    likedBeer: {
      type: [],
      required: true
    },
    fetchBeer: {
      required: true
    },
    likeBeer: {
      required: true
    }
  }
}
</script>

<style scoped>
.beer {
  background-color: black;
  text-align: center;
}

.beer__title {
  padding-top: 2rem;
}

.beer__section {
  display: flex;
  justify-content: space-between;
  padding-left: 2rem;
  margin: 1rem 0;
}

.beer__btns {
  padding-bottom: 2rem;
}
</style>