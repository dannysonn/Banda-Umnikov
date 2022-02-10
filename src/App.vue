<template>
  <div class="app">
    <div class="person">

      <h1 class="app__title">Profile</h1>

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

    <div class="beer">
      <h2>Proposed beer</h2>
      <div class="beer__brand">
        <span><b>Brand:</b> {{beer.brand}}</span>
      </div>
      <div class="beer__name">
        <span><b>Name:</b> {{beer.name}}</span>
      </div>
      <div class="beer__style">
        <span><b>Style:</b> {{beer.style}}</span>
      </div>
      <div class="beer__hop">
        <span><b>Hop:</b> {{beer.hop}}</span>
      </div>
      <div class="beer__yeast">
        <span><b>Yeast:</b> {{beer.yeast}}</span>
      </div>
      <div class="beer__malts">
        <span><b>Malts:</b> {{beer.malts}}</span>
      </div>
      <div class="beer__ibu">
        <span><b>Ibu:</b> {{beer.ibu}}</span>
      </div>
      <div class="beer__alcohol">
        <span><b>alcohol:</b> {{beer.alcohol}}</span>
      </div>
      <div class="beer__blg">
        <span><b>Blg:</b> {{beer.blg}}</span>
      </div>
      <div v-if="likedBeer.length > 0" class="beer__like">
        <span><b>Favorite beer:</b> {{likedBeer}}</span>
      </div>
<!--      brand: '',-->
<!--      name: '',-->
<!--      style: '',-->
<!--      hop: '',-->
<!--      yeast: '',-->
<!--      malts: '',-->
<!--      ibu: '',-->
<!--      alcohol: '',-->
<!--      blg: '',-->
      <dislike-button @click="fetchBeer" style="background-color: darkmagenta"/>
      <like-button @click="likeBeer" />
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
import DislikeButton from "./components/DislikeButton";
import LikeButton from "./components/LikeButton";

export default {
  components: {
    LikeButton,
    DislikeButton,
    PersonSubscription, PersonAddress, PersonEmployment, PersonContacts, PersonInfo, PersonAvatar},
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
      beer: {
        brand: '',
        name: '',
        style: '',
        hop: '',
        yeast: '',
        malts: '',
        ibu: '',
        alcohol: '',
        blg: '',
      },
      likedBeer: [],
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
    },
    likeBeer() {
        this.likedBeer.push(this.beer.name);
        this.fetchBeer();
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
.beer {
}
</style>
