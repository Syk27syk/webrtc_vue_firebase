<!-- eslint-disable -->
<template>
  <div class="home">
    <h1>Home</h1>
    <p>Hello {{ user }}! </p>
  </div>
</template>

<!--
<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App" />
  </div>
</template>
-->

<script>
// @ is an alias to /src
// eslint-disable-next-line
import HelloWorld from "@/components/HelloWorld.vue";
// eslint-disable-next-line
import db from "../db.js";

export default {
  // eslint-disable-next-line
  name: "HomeView",
  // eslint-disable-next-line
  data: function() {
    return {
      // eslint-disable-next-line
      user: null,
      // eslint-disable-next-line
    };
  },
  mounted() {
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
  },
  components: {
    // eslint-disable-next-line
    HelloWorld,
    // eslint-disable-next-line
  },
  // eslint-disable-next-line
};
</script>
