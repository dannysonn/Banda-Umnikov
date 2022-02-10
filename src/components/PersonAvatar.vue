<template>
  <div class="person__avatar">
    <img :src="avatar" alt="User avatar">
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
  width: 100%;
  max-width: 150px;
  height: 150px;

  border-radius: 50%;
  background: black;

  transition: transform .4s linear;
}

img:hover {
  transform: scale(1.1);
}

.person__avatar {
  text-align: center;
  padding-top: 2em;
}

@media (max-width: 700px) {
  img {
    max-width: 125px;
    height: 125px;
  }
}

@media (max-width: 550px) {
  img {
    max-width: 90px;
    height: 90px;
  }
}



</style>