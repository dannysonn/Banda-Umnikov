<template>
  <aside class="sidebar">
    <person-avatar :avatar="avatar"/>
    <div class="user__name">
      <div>
        <b>{{ first_name }}</b>
      </div>
      <div>
        <b>{{ last_name }}</b>
      </div>
    </div>
    <div class="favorite__beer">
      <div v-if="likedBeer.length > 0">
        <span><b>Favorite beer:</b> {{ Array.from(new Set(likedBeer)).map(item => '"' + item + '"').toString() }}</span>
      </div>
      <div v-else>
        <span><b>Favorite beer:</b> favorite beer will be here...</span>
      </div>
    </div>
  </aside>
</template>

<script>
import personAvatar from "./PersonAvatar";
export default {
  components: {
    personAvatar
  },
  props: {
    avatar: {
      type: String,
      required: true,
    },
    first_name: {
      type: String,
      required: true,
    },
    last_name: {
      type: String,
      required: true,
    },
    likedBeer: {
      type: String,
      required: true,
    },
  }
}
</script>

<style scoped>
.sidebar {
  width: 30%;

  background-color: #1b1b1b;

  text-align: center;
}

.user__name {
  margin-top: 1rem;
}

.favorite__beer {
  margin-top: 2rem;
}
</style>