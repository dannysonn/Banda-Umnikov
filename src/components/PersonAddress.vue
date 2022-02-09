<template>
  <div class="person__item">
    <div class="address">
      <h2>Address</h2>
      <div class="address__city">
        <h4>City:</h4>
        {{ city }}
      </div>
      <div class="address__street_name">
        <h4>Street name:</h4>
        {{ street_name }}
      </div>
      <div class="address__street_address">
        <h4>Street address:</h4>
        {{ street_address }}
      </div>
      <div class="address__zip_code">
        <h4>Zip code:</h4>
        {{ zip_code }}
      </div>
      <div class="address__state">
        <h4>State:</h4>
        {{ state }}
      </div>
      <div class="address__country">
        <h4>Country:</h4>
        {{ country }}
      </div>
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
.address {
}
</style>