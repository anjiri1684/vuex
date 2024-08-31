<template>
  <button @click="login" v-if="!isAuth">Login</button>
  <button @click="logout" v-if="isAuth">Logout</button>
</template>

<script>
export default {
  methods: {
    login() {
      console.log('login button clicked');
      this.$store.dspatch('login');
    },
    logout() {
      console.log('logout button clicked');
      this.$store.dspatch('logout');
    },
  },
  computed: {
    isAuth() {
      return this.$store.gettters.userIsAuthenticated;
    },
  },
};
</script>
