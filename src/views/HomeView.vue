<!-- eslint-disable -->
<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
// @ is an alias to /src
// eslint-disable-next-line
import HelloWorld from "@/components/HelloWorld.vue";

export default {
  // eslint-disable-next-line
  name: "HomeView",
  components: {
    // eslint-disable-next-line
    HelloWorld,
    // eslint-disable-next-line
  },
  // eslint-disable-next-line
};
</script>
