<template>
  <v-app>
    <v-container>
      <v-toolbar app class="lime lighten-4">
        <v-toolbar-title><a href="/">Quiz App</a></v-toolbar-title>
        <v-spacer></v-spacer>

        <v-toolbar-items class="hidden-sm-and-down">
          <v-btn v-if="loggedIn == true" flat to="/">All tests</v-btn>
          <v-btn v-if="loggedIn == true" flat to="/about">Links</v-btn>
          <v-btn v-if="loggedIn == true" flat @click="submitLogout"
            >Logout</v-btn
          >
          <v-btn v-if="loggedIn == false" to="/login" flat>Login</v-btn>
          <v-btn v-if="loggedIn == false" to="/register" flat>Register</v-btn>
          <v-btn v-if="isAdmin == true" to="/create-quiz" flat
            >Create quiz</v-btn
          >
          <v-avatar v-if="loggedIn == true" color="lime" style="margin: 8px 0">
            <img
              src="https://img.icons8.com/small/16/000000/user-male-circle.png"
              style="width: 24px; height: 24px"
            />
          </v-avatar>
        </v-toolbar-items>
      </v-toolbar>
      <v-content>
        <router-view></router-view>
      </v-content>
    </v-container>
    <v-footer app></v-footer>
  </v-app>
</template>

<script>
import { mapActions, mapGetters } from "vuex";

export default {
  name: "app",
  data() {
    return {};
  },

  methods: {
    ...mapActions("user", {
      logout: "logout",
    }),

    submitLogout() {
      this.logout().then((response) => {
        this.$router.replace("login");
        location.reload();
      });
    },
  },

  mounted() {
    console.log(this.$store);
  },

  computed: {
    ...mapGetters("user", ["isAdmin", "loggedIn"]),
  },
};
</script>

<style>
input:hover,
input:hover + label,
button:hover {
  cursor: pointer;
}
.primary--text.v-input,
.primary--text.v-label {
  color: #827717 !important;
}
.primary.v-progress-linear__background,
.primary.v-progress-linear__bar__indeterminate.short,
.primary.v-progress-linear__bar__indeterminate.long {
  background-color: #827717 !important;
  border-color: #827717 !important;
}
.application {
  background-color: #fff !important;
}
.v-toolbar__item {
  align-items: center;
}
.v-btn.v-btn__main {
  background-color: #f9fbe7 !important;
  border: 1px solid #827717;
  border-radius: 12px !important;
  min-width: 100px;
  padding: 15px 40px;
  height: 50px;
}
.v-btn.v-btn__main:hover {
  background-color: #827717 !important;
  cursor: pointer;
}
.v-btn.v-btn__main .v-btn__content {
  color: #827717 !important;
  font-size: 16px;
}
.v-btn.v-btn__main:hover .v-btn__content,
.v-btn.v-btn__main:focus .v-btn__content {
  color: #fff !important;
}
.v-toolbar__title a {
  text-decoration: none;
  color: black;
}

@media only screen and (min-width: 1904px) {
  .container {
    max-width: 1440px !important;
  }
}
</style>
