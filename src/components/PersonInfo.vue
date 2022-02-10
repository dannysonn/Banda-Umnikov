<template>
  <div class="person__item">
    <div class="section__title">Main info</div>
    <div class="info__section">
      <span>First name</span>
      <span><b>{{ first_name }}</b></span>
    </div>
    <div class="info__section">
      <span>Last name</span>
      <span><b>{{ last_name }}</b></span>
    </div>
    <div class="info__section">
      <span>Username</span>
      <span><b>{{ username }}</b></span>
    </div>
    <div class="info__section">
      <span>Gender</span>
      <span><b>{{ gender }}</b></span>
    </div>
    <div class="info__section">
      <span>Date of Birth</span>
      <span><b>{{ birthday }}</b></span>
    </div>
  </div>
</template>

<script>
export default {
  name: "person-info",
  props: {
    username: {
      type: String,
      required: true
    },
    first_name: {
      type: String,
      required: true
    },
    last_name: {
      type: String,
      required: true
    },
    gender: {
      type: String,
      required: true
    },
    birthday: {
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

.info__section {
  display: flex;
  justify-content: space-between;

  padding: 0 0 1rem;
  margin: 1rem 0;

  border-bottom: 1px solid #B3B3B3;
  text-align: left;
}

.info__section span:first-child {
  color: #B3B3B3;
}

@media (max-width: 550px) {
  .info__section {
    display: flex;
    flex-wrap: wrap;
  }
}

@media (max-width: 450px) {
  .info__section {
    flex-wrap: wrap;
  }
  .info__section span {
    width: 100%;
  }
}
</style>