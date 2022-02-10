<template>
<button>
  {{ text }}
</button>
</template>

<script>
export default {
  props: {
    text: {
      type: String,
      require: true,
    }
  }
}
</script>

<style scoped>
button {
  width: 100px;
  color: white;
  text-transform: uppercase;

  margin: 10px;
  padding: 10px;
}
</style>