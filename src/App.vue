<template>
  <div id="app">
    <Navigation :user="user" />
    <!--
    <nav>
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </nav>
    -->
    <router-view :user="user" />
  </div>
</template>

<script>
// eslint-disable-next-line prettier/prettier
import db from './db.js';
// eslint-disable-next-line prettier/prettier
import Navigation from '@/components/Navigation';
// eslint-disable-next-line prettier/prettier
import Firebase from 'firebase/compat/app';

export default {
  // eslint-disable-next-line
  name: 'App',
  // eslint-disable-next-line
  data: function() {
    return {
      // eslint-disable-next-line
      user: null,
      // eslint-disable-next-line
    };
  },
  mounted() {
    Firebase.auth().onAuthStateChanged((user) => {
      if (user) {
        this.user = user;
      }
    });
    /*
    // eslint-disable-next-line
    db.collection('users')
      // eslint-disable-next-line
      .doc('AHFJ4wUrnhgh5mpddw74')
      // eslint-disable-next-line
      .get()
      // eslint-disable-next-line
      .then((snapshot) => {
        // eslint-disable-next-line
        this.user = snapshot.data().name;
        // eslint-disable-next-line
      });
    */
  },
  components: {
    // eslint-disable-next-line prettier/prettier
    Navigation,
    // eslint-disable-next-line prettier/prettier
  },
  // eslint-disable-next-line prettier/prettier
};
</script>

<style lang="scss">
$primary: #5f2882;
// eslint-disable-next-line prettier/prettier
@import "node_modules/bootstrap/scss/bootstrap";
</style>

<!--
<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
-->
