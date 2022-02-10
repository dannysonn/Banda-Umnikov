<template>
  <div class="person__item">
    <div class="section__title">Your plan</div>
    <div class="subscription">
      <div class="subscription__plan">
        <h2>{{ plan }}</h2>
      </div>
      <div class="subscription__section">
        <span>Status</span>
        <span><b>{{ status }}</b></span>
      </div>
      <div class="subscription__section">
        <span>Payment</span>
        <span><b>{{ payment }}</b></span>
      </div>
      <div class="subscription__section">
        <span>Term</span>
        <span><b>{{ term }}</b></span>
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
* {
  color: black;
}

.subscription {
  border: 1px solid #869940;
}

.subscription__plan {
  padding: 2rem;

  background-color: #869940;
}

.subscription__section {
  display: flex;
  justify-content: space-between;
  margin: 2rem;

  text-align: left;
}

.subscription__section span:first-child {
  color: #B3B3B3;
}

@media (max-width: 450px) {
  .subscription__section {
    flex-wrap: wrap;
  }
  .subscription__section span {
    width: 100%;
  }
}
</style>