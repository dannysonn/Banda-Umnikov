<template>
  <div class="person__item">
    <div class="section__title">Employment</div>
    <div class="employment__section">
      <span>Title</span>
      <span><b>{{ title }}</b></span>
    </div>
    <div class="employment__section">
      <span>Key skill</span>
      <span><b>{{ key_skill }}</b></span>
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
* {
  color: black;
}

.employment__section {
  display: flex;
  justify-content: space-between;

  padding: 0 0 1rem;
  margin: 1rem 0;

  border-bottom: 1px solid #B3B3B3;
  text-align: left;
}

.employment__section span:first-child {
  color: #B3B3B3;
}

@media (max-width: 550px) {
  .employment__section {
    display: flex;
    flex-wrap: wrap;
  }
}

@media (max-width: 450px) {
  .employment__section {
    flex-wrap: wrap;
  }
  .employment__section span {
    width: 100%;
  }
}

</style>