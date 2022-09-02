<!-- eslint-disable -->
<template>
  <div class="home">
    <!--
    <h1>Home</h1>
    <p>Hello {{ user }}! </p>
    -->
    <div class="mt-3">
      <div class="text-center" v-if="user">
        Welcome back<span class="font-weight-bold text-info">{{ user.displayName }}</span
        >, <a href="#" role="button" class="text-primary" @click="$emit('logout')">logout</a>
      </div>
      <div class="container text-center">
        <div class="row justify-content-center">
          <div class="col-10 col-md-10 col-lg-8 col-xl-7">
            <h4 class="display-4 text-primary mb-2">Video Chat</h4>
            <p class="lead">
              This app uses Firebase for real time communication and WebRTC to create video chats
              between multiple users, allowing you to create rooms for your meetings and invite
              attendees.
            </p>
            <router-link class="btn btn-outline-primary m-2" to="/login" v-if="!user">Log In</router-link>
            <router-link class="btn btn-outline-primary m-2" to="/register" v-if="!user">Register</router-link>
          </div>
        </div>
      </div>
    </div>
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
  /*
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
  */
  components: {
    // eslint-disable-next-line
    HelloWorld,
    // eslint-disable-next-line
  },
  // eslint-disable-next-line
};
</script>
