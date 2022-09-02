<!-- eslint-disable -->
<template>
    <div>
    <nav class="navbar navbar-expand bg-primary navbar-dark">
        <div class="container-fluid">
        <router-link class="navbar-brand" to="/"
            ><span class="h2 pr-1">Video Chat</span>
            <span class="navbar-text small">
            : Hi <span class="font-weight-bold text-white">{{ user }}</span></span
            >
        </router-link>
        <div class="navbar-nav ml-auto">
            <router-link class="nav-item nav-link" to="/login">log in</router-link>
        </div>
        </div>
    </nav>
    </div>
<!--
  <div>
    <nav>
      <router-link to="/">Home</router-link>
      <router-link to="/login">Login</router-link>
    </nav>
  </div>
-->
</template>

<script>
export default {
  // eslint-disable-next-line
  name: "Navigation",
  // eslint-disable-next-line
  props: ["user"],
  // eslint-disable-next-line
};
</script>
