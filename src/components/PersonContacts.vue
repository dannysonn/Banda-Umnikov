<template>
  <div class="person__item">
    <div class="section__title">Contacts</div>
    <div class="contacts__section">
      <span>Email</span>
      <span><b>{{ email }}</b></span>
    </div>
    <div class="contacts__section">
      <span>Phone number:</span>
      <span><b>{{ phone_number }}</b></span>
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
* {
  color: black;
}

.contacts__section {
  display: flex;
  justify-content: space-between;

  padding: 0 2rem 1rem;
  margin: 1rem 0;

  border-bottom: 1px solid #B3B3B3;
}

.contacts__section span:first-child {
  color: #B3B3B3;
}
</style>