<template>
    <div>

        <banner-slider />
        <v-container grid-list-md text-center>
            <v-layout wrap>
                <bar-loader 
                    class="custom-class" 
                    :color="spinnerColor" 
                    v-if="loading == false" 
                    :size="size" 
                    :sizeUnit="sizeUnit">
                </bar-loader>
                
                <v-flex v-for="quiz in quizData" :key="quiz.title" col-md-3 col-12>
                    <v-hover v-slot:default="{ hover }">
                        <v-card
                            :elevation="hover ? 12 : 2"
                            class="mx-auto"
                            max-width="350"
                            dark
                        >
                            <v-card-title> 
                                <h3>{{ quiz.title }}</h3>
                            </v-card-title>

                            <v-card-text> 
                                <div>{{ quiz.description }}</div>
                            </v-card-text>
                            <v-card-actions class="justify-center">
                                <v-btn flat :to="{ name: 'single-quiz', params: { id: quiz.id } }" class="btn-primary v-btn__main">See Details</v-btn>
                            </v-card-actions>
                        </v-card>
                    </v-hover>
                </v-flex>
            </v-layout>
        </v-container>

    </div>
</template>

<script>

import {mapActions} from 'vuex'

export default {

    data() {
        return {
            quizData: [],
            loading: false,
            spinnerColor: '#bada55',
            sizeUnit: 'px',
            size: 130
        }
    },
  
    created() {
        this.fetchQuizFromState()
    },

    methods:{
        ...mapActions('quiz', {
            fetchAllQuizes: 'fetchAllQuizes'
        }),

        fetchQuizFromState() {
            
            this.fetchAllQuizes().then(response => {
                return new Promise((resolve, reject) => {
                    setTimeout(() => {
                        this.quizData = this.$store.state.quiz.allQuizes
                        this.loading = true
                        resolve()
                    }, 1000)
                })
            })
        },

        pageRefresh(){
            location.reload()
        },
    }
}

</script>

<style scoped>


.container.grid-list-md .layout .flex{
    padding: 10px;
}
.button{
  margin-left: 0px  
}
.theme--dark.v-sheet{
    display: flex;
    flex-direction: column;
    height: 100%;
    background-color: transparent;
    border: 2px solid #dadada;
}
.v-card__title{
    font-size: 18px;
    color: #F95A2C;

}
.v-card__text{
    color: #18191F;
    flex: 1 0 auto;
}
.v-card__actions{
    padding-bottom: 10px
}

</style>



