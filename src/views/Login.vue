<!-- eslint-disable -->
<template>
  <div id="login">
    <form class="mt-3" @submit.prevent="login">
      <div class="container">
        <div class="row justify-content-center">
          <div class="col-lg-6">
            <div class="card bg-light">
              <div class="card-body">
                <h3 class="font-weight-light mb-3">Log in</h3>
                <section class="form-group">
                  <div class="col-12 alert alert-danger px-3" v-if="error">
                    {{ error }}
                  </div>
                  <label class="form-control-label sr-only" for="Email">Email</label>
                  <input
                    required
                    class="form-control"
                    type="email"
                    id="email"
                    placeholder="Email"
                    v-model="email"
                  />
                </section>
                <section class="form-group">
                  <input
                    required
                    class="form-control"
                    type="password"
                    placeholder="Password"
                    v-model="password"
                  />
                </section>
                <div class="form-group text-right mb-0">
                  <button class="btn btn-primary" type="submit">Log in</button>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </form>
    <p class="text-center mt-2">
      or
      <router-link to="/register">register</router-link>
    </p>
  </div>
</template>

<script>
// eslint-disable-next-line
import Firebase from 'firebase/compat/app';

export default {
  data: function () {
    return {
      email: null,
      password: null,
      // eslint-disable-next-line
      error: null,
      // eslint-disable-next-line
    };
  },
  methods: {
    login: function () {
      const info = {
        email: this.email,
        // eslint-disable-next-line
        password: this.password,
        // eslint-disable-next-line
      };
      Firebase.auth()
        .signInWithEmailAndPassword(info.email, info.password)
        .then(
          () => {
            // eslint-disable-next-line
            this.$router.push("/");
          },
          // eslint-disable-next-line
          (error) => {
            // eslint-disable-next-line
            this.error = error.message;
          }
          // eslint-disable-next-line
        );
      // eslint-disable-next-line
    },
    // eslint-disable-next-line
  },
  // eslint-disable-next-line
};
</script>
