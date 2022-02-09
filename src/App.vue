<template>
  <div class="app">
    <div class="person">

      <h1 class="app__title">Personal account</h1>

      <person-avatar :avatar="user.avatar"/>

      <person-info :username="user.username" :first_name="user.first_name" :last_name="user.last_name"
                   :gender="user.gender" :birthday="user.date_of_birth"/>

      <person-contacts :email="user.email" :phone_number="user.phone_number"/>

      <person-employment :title="user.employment.title" :key_skill="user.employment.key_skill" />

      <person-address :city="user.address.city" :country="user.address.country" :state="user.address.state"
                      :street_address="user.address.street_address" :street_name="user.address.street_name" :zip_code="user.address.zip_code" />

      <person-subscription :plan="user.subscription.plan" :payment="user.subscription.payment_method"
                           :status="user.subscription.status" :term="user.subscription.term"/>

    </div>

    <div>
      {{ beer }}
    </div>
  </div>
</template>

<script>
import axios from "axios";
import PersonAvatar from "./components/PersonAvatar";
import PersonInfo from "./components/PersonInfo";
import PersonContacts from "./components/PersonContacts";
import PersonEmployment from "./components/PersonEmployment";
import PersonAddress from "./components/PersonAddress";
import PersonSubscription from "./components/PersonSubscription";

export default {
  components: {PersonSubscription, PersonAddress, PersonEmployment, PersonContacts, PersonInfo, PersonAvatar},
  data() {
    return {
      user: {
        first_name: '',
        last_name: '',
        _password: '',
        username: '',
        email: '',
        avatar: '',
        gender: '',
        phone_number: '',
        social_insurance_number: '',
        date_of_birth: '',
        employment: {
          title: '',
          key_skill: '',
        },
        address: {
          city: '',
          street_name: '',
          street_address: '',
          zip_code: '',
          state: '',
          country: '',
          coordinates: {
            lat: '',
            ing: '',
          },
        },
        credit_card: {
          cc_number: '',
        },
        subscription: {
          plan: '',
          status: '',
          payment_method: '',
          term: '',
        },
      },
      beer: {}
    }
  },
  methods: {
    async fetchUser() {
      try {
        const response = await axios.get('https://random-data-api.com/api/users/random_user');
        this.user = response.data;
      } catch (e) {
        console.log(e);
      }
    },
    async fetchBeer() {
      try {
        const response = await axios.get('https://random-data-api.com/api/beer/random_beer');
        console.log(response);
        this.beer = response.data;
        console.log(this.beer);
      } catch (e) {
        console.log(e);
      }
    }
  },
  mounted() {
    this.fetchUser();
    this.fetchBeer();
  }
}
</script>

<style>
* {
  padding: 0;
  margin: 0;
  border: 0;
  box-sizing: content-box;

  color: white;
  font-family: 'Montserrat', sans-serif;
}

.app {}

.app__title {
  width: 100%;
  height: 2em;

  background: black;

  text-align: center;
  line-height: 2em;
}

body {
  background: #212c39;
}

.person {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}

.person__item {
  width: 100%;
  margin: 2rem;
}
</style>
