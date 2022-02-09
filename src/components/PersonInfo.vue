<template>
  <div class="person__item">
    <div class="person__info">
      <h2>Main info</h2>
      <div class="person__firstName">
        <h4>First name:</h4>
        <span>{{ first_name }}</span>
      </div>
      <div class="person__lastName">
        <h4>Last name:</h4>
        {{ last_name }}
      </div>
      <div class="person__username">
        <h4>Username:</h4>
        {{ username }}
      </div>
      <div class="person__gender">
        <h4>Gender:</h4>
        {{ gender }}
      </div>
      <div class="person__birthday">
        <h4>Date of Birth:</h4>
        {{ birthday }}
      </div>
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
  .person__firstName {
    display: flex;
  }
</style>