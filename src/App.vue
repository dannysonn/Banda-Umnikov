<template>
  <div class="app">
    <header>
      <h2 class="app__title">Profile</h2>
    </header>

    <div class="container">
      <welcome/>

      <main>
        <sidebar :avatar="user.avatar" :last_name="user.last_name"
                 :first_name="user.first_name" :liked-beer="likedBeer"/>

        <div class="person">

          <div class="person__item">
            <h2 class="account__overview">Account overview</h2>
          </div>

          <person-info :username="user.username" :first_name="user.first_name" :last_name="user.last_name"
                       :gender="user.gender" :birthday="user.date_of_birth"/>

          <person-contacts :email="user.email" :phone_number="user.phone_number"/>

          <person-employment :title="user.employment.title" :key_skill="user.employment.key_skill"/>

          <person-address :city="user.address.city" :country="user.address.country" :state="user.address.state"
                          :street_address="user.address.street_address" :street_name="user.address.street_name"
                          :zip_code="user.address.zip_code"/>

          <person-subscription :plan="user.subscription.plan" :payment="user.subscription.payment_method"
                               :status="user.subscription.status" :term="user.subscription.term"/>

        </div>
      </main>
    </div>

    <footer>
      <div class="beer">
        <beer :name="beer.name" :brand="beer.brand" :blg="beer.blg" :alcohol="beer.alcohol"
              :ibu="beer.ibu" :malts="beer.malts" :yeast="beer.yeast" :style="beer.style" :hop="beer.hop"
              :likedBeer="likedBeer" :fetchBeer="fetchBeer" :likeBeer="likeBeer"
        />
      </div>
    </footer>
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
import BeerButton from "./components/BeerButton";
import Beer from "./components/Beer";
import Welcome from "./components/Welcome";
import Sidebar from "./components/Sidebar";

export default {
  components: {
    Sidebar,
    Welcome,
    Beer,
    BeerButton,
    PersonSubscription, PersonAddress, PersonEmployment, PersonContacts, PersonInfo, PersonAvatar
  },
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
  box-sizing: border-box;

  color: white;
  font-family: 'Montserrat', sans-serif;
  font-size: 16px;
}

h1 {
  font-size: 72px;
}

h2 {
  font-size: 32px;
}

.container {
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
}

.account__overview {
  color: black;
  margin: 1rem 0 0;
  text-align: left;
}

main {
  display: flex;
}

.app {
}

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
  width: 70%;

  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;

  background-color: white;

  text-align: center;
}

.person__item {
  width: 100%;
  max-width: 550px;
  margin: 2rem auto;
}

.person__item:first-child {
  margin-top: 5rem;
}

.section__title {
  font-size: 20px;
  font-weight: bold;

  text-align: left;

  margin-bottom: 2rem;
}
</style>
