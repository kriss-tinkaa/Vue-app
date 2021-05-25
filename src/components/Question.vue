<template>
    <v-card>
        <v-card-title primary-title>
            <h2>
                Question {{ questionNumber }}: {{ question.text }} 
            </h2>
        </v-card-title>    
        
        <v-divider></v-divider> 
        
        <v-card-title>
            <v-list v-if="question.type === 'tf'">
                <input type="radio" name="currentQuestion" id="trueAnswer" v-model="answer" value="t"><label for="trueAnswer"> True</label><br/>
                <input type="radio" name="currentQuestion" id="falseAnswer" v-model="answer" value="f"><label for="falseAnswer"> False</label><br/>
            </v-list>

            <v-list v-if="question.type === 'mc'">
                <div v-for="(mcanswer, index) in question.answers" :key="index">
                    <input type="radio" :id="'answer'+index" name="currentQuestion" v-model="answer" :value="mcanswer"><label :for="'answer'+index"> {{mcanswer}}</label><br/>
                </div>
            </v-list>
        </v-card-title>

        <v-card-actions>
            <v-btn color="btn-primary v-btn__main" @click="submitAnswer">Answer</v-btn>
        </v-card-actions>
    </v-card>
</template>

<script>
export default {
    data() {
        return {
            answer:''
        }
    },
	props:['question','question-number'],
	methods:{
		submitAnswer:function() {
			this.$emit('answer', {answer:this.answer});
            this.answer = null;
		}
	}
}
</script>

<style scoped>

.v-card{
    min-height: 215px;
}
.v-list > div{
    padding: 10px 0;
}
.v-list label{
    font-size: 16px;
}

.v-card__actions{
    margin-left: 8px
}

</style>
