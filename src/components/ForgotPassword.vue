<template>
    <v-layout align-center justify-center column fill-height>
        <form @submit.prevent="forgetPassword">
            <h3>Forgot Password</h3>
            <v-text-field
                v-model="user.email"
                label="E-mail"
                required
                darken-4
            ></v-text-field>  
            <button type="submit" class="v-btn v-btn__main">Reset password</button>
        </form>
    </v-layout>   
</template>

<script>
import firebase from "firebase";

export default {
  data() {
    return {
      user: {   
        email: ''
      }
    };
  },
  methods: {
    forgetPassword() {
        firebase
        .auth()
        .sendPasswordResetEmail(this.user.email)
        .then(() => {
            alert('Check your registered email to reset the password!')
            this.user = {   
              email: ''
            }
        }).catch((error) => {
          alert(error)
        })
    }
  }
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

.v-btn.v-btn__main {
  display: flex;
  margin: 0 auto;
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

</style>