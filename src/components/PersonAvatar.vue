<template>
  <div class="person__item">
    <div class="person__avatar">
      <img :src="avatar" alt="User avatar">
    </div>
  </div>
</template>

<script>
export default {
  props: {
    avatar: {
      type: String,
      required: true
    }
  }
}
</script>

<style scoped>
img {
  border-radius: 50%;
  border: 2px solid white;
  background: rgba(31, 31, 31, 0.5);
}
</style>