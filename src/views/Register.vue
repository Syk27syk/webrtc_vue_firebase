<!-- eslint-disable -->
<template>
  <div>
    <form class="mt-3" @submit.prevent="register">
      <div class="container">
        <div class="row justify-content-center">
          <div class="col-lg-8">
            <div class="card bg-light">
              <div class="card-body">
                <h3 class="font-weight-light mb-3">Register</h3>
                <div class="form-row">
                  <div v-if="error" class="col-12 alert alert-danger px-3">
                    {{ error }}
                  </div>
                  <section class="col-sm-12 form-group">
                    <label class="form-control-label sr-only" for="displayName"
                      >Display Name</label
                    >
                    <input
                      class="form-control"
                      type="text"
                      id="displayName"
                      placeholder="Display Name"
                      name="displayName"
                      required
                      v-model="displayName"
                    />
                  </section>
                </div>
                <section class="form-group">
                  <label class="form-control-label sr-only" for="email"
                    >Email</label
                  >
                  <input
                    class="form-control"
                    type="email"
                    id="email"
                    placeholder="Email Address"
                    required
                    name="email"
                    v-model="email"
                  />
                </section>
                <div class="form-row">
                  <section class="col-sm-6 form-group">
                    <input
                      class="form-control"
                      type="password"
                      placeholder="Password"
                      v-model="passOne"
                    />
                  </section>
                  <section class="col-sm-6 form-group">
                    <input
                      class="form-control"
                      type="password"
                      required
                      placeholder="Repeat Password"
                      v-model="passTwo"
                    />
                  </section>
                </div>
                <div class="form-group text-right mb-0">
                  <button class="btn btn-primary" type="submit">
                    Register
                  </button>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </form>
    <p class="text-center mt-2">
      or
      <router-link to="/login">login</router-link>
    </p>
  </div>
</template>

<script>
// eslint-disable-next-line
import Firebase from 'firebase/compat/app';

export default {
  data: function () {
    return {
      displayName: null,
      email: null,
      passOne: null,
      passTwo: null,
      // eslint-disable-next-line
      error: null,
      // eslint-disable-next-line
    };
  },
  methods: {
    register: function () {
      const info = {
        email: this.email,
        password: this.passTwo,
        // eslint-disable-next-line
        displayName: this.displayName,
        // eslint-disable-next-line
      };
      if (!this.error) {
        // eslint-disable-next-line
        Firebase.auth().createUserWithEmailAndPassword(
          info.email,
          info.password
        );
        // eslint-disable-next-line
        then(
          // eslint-disable-next-line
          (userCredentials) => {
            // eslint-disable-next-line
            return userCredentials.user
              .updateProfile({
                // eslint-disable-next-line
                displayName: info.displayName,
              })
              .then(() => {
                // eslint-disable-next-line
                this.$router.replace('/')
                // eslint-disable-next-line
              });
          },
          // eslint-disable-next-line
          (error) => {
            // eslint-disable-next-line
            this.error = error.message;
          }
          // eslint-disable-next-line
        );
      }
      // eslint-disable-next-line
    },
  },
  watch: {
    passTwo: function () {
      // eslint-disable-next-line
      if (this.passOne !=='' && this.passTwo !== '' && this.passTwo !== this.passOne) {
        // eslint-disable-next-line
        this.error = 'passwords must match'
      } else {
        // eslint-disable-next-line
        this.error = null;
      }
      // eslint-disable-next-line
    },
    // eslint-disable-next-line
  },
  // eslint-disable-next-line
};
</script>
