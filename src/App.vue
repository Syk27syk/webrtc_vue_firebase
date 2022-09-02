<template>
  <div id="app">
    <Navigation />
    <!--
    <nav>
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </nav>
    -->
    <router-view />
  </div>
</template>

<script>
// eslint-disable-next-line prettier/prettier
import Navigation from '@/components/Navigation'

export default {
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
@import 'node_modules/bootstrap/scss/bootstrap';
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
