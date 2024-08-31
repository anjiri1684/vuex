<template>
  <base-container title="Vuex" v-if="isAuth">
    <the-counter></the-counter>
    <favorites-value></favorites-value>
    <button @click="addOne">Add 10</button>
    <change-counter></change-counter>
  </base-container>
  <base-container title="Auth">
    <user-auth></user-auth>
  </base-container>
</template>

<script>
import BaseContainer from './components/BaseContainer.vue';
import ChangeCounter from './components/ChangeCounter.vue';
import FavoritesValue from './components/FavoritesValue.vue';
import TheCounter from './components/TheCounter.vue';
import UserAuth from './components/UserAuth.vue';

export default {
  components: {
    BaseContainer,
    TheCounter,
    ChangeCounter,
    FavoritesValue,
    UserAuth,
  },
  computed: {
    isAuth() {
      return this.$store.gettters.userIsAuthenticated;
    },
  },

  methods: {
    addOne() {
      // this.$store.commit('increase', { value: 10 });
      this.$store.dispatch({
        type: 'increase',
        value: 10,
      });
    },
  },
};
</script>

<style>
* {
  box-sizing: border-box;
}

html {
  font-family: sans-serif;
}

body {
  margin: 0;
}
</style>
