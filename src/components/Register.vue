<template>
    <div>
        <v-layout align-center justify-center column fill-height>
             <v-img max-width="400px" width="100%" :src="require('@/assets/eng.jpg')"></v-img>

            <v-text-field
                v-model="email"
                label="E-mail"
                required
            ></v-text-field>  
            <v-text-field
                v-model="password"
                :type="'password'"
                label="Password"
                hint="At least 8 characters"
                required
            ></v-text-field>  
            <v-btn @click="submitRegister" class="v-btn__main">Register</v-btn>
            
            <div class="custom-error">
                <p v-if="errors.length">
                    <b>Please correct the following error(s):</b>
                    <ul>
                    <li v-for="error in errors" :key="error">{{ error }}</li>
                    </ul>
                </p>
            </div>

        </v-layout>   
    </div>
</template>

<script>
import { mapActions } from 'vuex';

export default {
    name: 'register',
    data() {
        return{
            errors: [],
            password: '',
            email: ''
        }
    },  
    methods: {
        ...mapActions('user', {
            resgister: 'resgister'
        }),

        submitRegister(e){
            this.errors = [];

            if (!this.email) {
                this.errors.push('Email required.');
            }
            if (!this.password) {
                this.errors.push('Password required.');
            }

            e.preventDefault();

            this.resgister({
                email: this.email,
                password: this.password
            })
            .then(response => {
                if( this.$store.state.user.loggedIn ){
                    this.$router.replace('/')   
                    location.reload()       
                }
            }, error => {
                this.errors.push(error.message);
            })
        }
    }
}
</script>

<style scoped>

    .custom-error{
        margin-top: 10px;
    }

    .custom-error p{
        color: red
    }

</style>
