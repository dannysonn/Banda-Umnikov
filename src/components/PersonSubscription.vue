<template>
  <div class="person__item">
    <div class="subscription">
      <h2>Subscription</h2>
      <div class="subscription__plan">
        <h4>Plan:</h4>
        {{ plan }}
      </div>
      <div class="subscription__status">
        <h4>Status:</h4>
        {{ status }}
      </div>
      <div class="subscription__payment">
        <h4>Payment:</h4>
        {{ payment }}
      </div>
      <div class="subscription__term">
        <h4>Term:</h4>
        {{ term }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    plan: {
      type: String,
      required: true
    },
    status: {
      type: String,
      required: true
    },
    payment: {
      type: String,
      required: true
    },
    term: {
      type: String,
      required: true
    },
  }
}
</script>

<style scoped>
.subscription {

}
</style>