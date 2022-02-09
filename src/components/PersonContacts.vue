<template>
  <div class="person__item">
    <div class="contacts">
      <h2>Contacts</h2>
      <div class="contacts__email">
        <h4>Email:</h4>
        {{ email }}
      </div>
      <div class="contacts__phone">
        <h4>Phone number:</h4>
        {{ phone_number }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "PersonContacts",
  props: {
    email: {
      type: String,
      required: true,
    },
    phone_number: {
      type: String,
      required: true,
    }
  }
}
</script>

<style scoped>

</style>