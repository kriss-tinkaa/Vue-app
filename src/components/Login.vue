<template>
    <div>
        <v-layout align-center justify-center column fill-height>
            <v-img max-width="400px" width="100%" :src="require('@/assets/eng.jpg')"></v-img>
            <v-form
                ref="form"
                v-model="valid"
                lazy-validation
              >
                  <v-text-field
                      v-model="email"
                      label="E-mail"
                      required
                      darken-4
                  ></v-text-field>  
                  <v-text-field
                      v-model="password"
                      label="Password"
                      :rules="emailRules"
                      :type="'password'"
                      required
                  ></v-text-field>  
                  
                  <div>
                    <v-btn @click="submitLogin" class="v-btn__main">Login</v-btn>
                    <p class="forgot-password text-right mt-2 mb-4">
                      <router-link to="/forgot-password">Forgot password ?</router-link>
                    </p>
                  </div>
                  <div class="custom-error">
                      <p v-if="errors.length">
                          <b>Please correct the following error(s):</b>
                          <ul>
                          <li v-for="error in errors" :key="error">{{ error }}</li>
                          </ul>
                      </p>
                  </div>
            </v-form>
        </v-layout>   
    </div>
</template>

<script>
import { mapActions } from "vuex";

export default {
  name: "login",
  data() {
    return {
      errors: [],
      password: "",
      email: "",
    };
  },
  methods: {
    ...mapActions("user", {
      login: "login",
    }),

    submitLogin(e) {
      this.errors = [];

      if (!this.email) {
        this.errors.push("Email required.");
      }
      if (!this.password) {
        this.errors.push("Password required.");
      }

      e.preventDefault();

      this.login({
        email: this.email,
        password: this.password,
      }).then(
        (response) => {
          if (this.$store.state.user.loggedIn) {
            this.$router.replace("/");
            location.reload();
          }
        },
        (error) => {
          this.errors.push(error.message);
        }
      );
    },
  },
};
</script>

<style scoped>
.theme--light.v-label {
  left: 12px;
}
.custom-error {
  margin-top: 10px;
}

.custom-error p {
  color: red;
}
.forgot-password{
  text-align: center;
}
.forgot-password a{
  color: #827717;
  text-decoration: none;
}
</style>
