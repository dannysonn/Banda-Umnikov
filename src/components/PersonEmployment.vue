<template>
  <div class="person__item">
    <div class="employment">
      <h2>Employment</h2>
      <div class="employment__title">
        <h4>Title:</h4>
        {{ title }}
      </div>
      <h4>Key skill:</h4>
      <div class="employment__key-skill">
        {{ key_skill }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true
    },
    key_skill: {
      type: String,
      required: true
    }
  }
}
</script>

<style scoped>
.employment {

}
</style>