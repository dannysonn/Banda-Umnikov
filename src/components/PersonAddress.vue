<template>
  <div class="person__item">
    <div class="section__title">Address</div>
    <div class="address__section">
      <span>City</span>
      <span><b>{{ city }}</b></span>
    </div>
    <div class="address__section">
      <span>Street name</span>
      <span><b>{{ street_name }}</b></span>
    </div>
    <div class="address__section">
      <span>Street address</span>
      <span><b>{{ street_address }}</b></span>
    </div>
    <div class="address__section">
      <span>Zip code</span>
      <span><b>{{ zip_code }}</b></span>
    </div>
    <div class="address__section">
      <span>State</span>
      <span><b>{{ state }}</b></span>
    </div>
    <div class="address__section">
      <span>Country</span>
      <span><b>{{ country }}</b></span>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    city: {
      type: String,
      required: true
    },
    street_name: {
      type: String,
      required: true
    },
    street_address: {
      type: String,
      required: true
    },
    zip_code: {
      type: String,
      required: true
    },
    state: {
      type: String,
      required: true
    },
    country: {
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

.address__section {
  display: flex;
  justify-content: space-between;

  padding: 0 0 1rem;
  margin: 1rem 0;

  border-bottom: 1px solid #B3B3B3;

  text-align: left;
}

.address__section span:first-child {
  color: #B3B3B3;
}

@media (max-width: 550px) {
  .address__section {
    display: flex;
    flex-wrap: wrap;
  }
}

@media (max-width: 450px) {
  .address__section {
    flex-wrap: wrap;
  }
  .address__section span {
    width: 100%;
  }
}
</style>