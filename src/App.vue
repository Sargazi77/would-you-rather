<template>
<div id="app">
  <whouldYouRatherQestion
  v-bind:questions="questions"
  v-on:answer-changed="userAnswers">
  </whouldYouRatherQestion>
  <div class="result"> 
      <h1>{{  ResultHeader }}</h1>
  </div>
   <div class="answers"> 
    <p>
     
      <ul>
        <li v-for="choice in userChoices" :key="choice"><span>{{choice}}</span></li>                
      </ul>
    </p>
    </div>

</div>
</template>

<script>
import whouldYouRatherQestion from './components/wouldYouRatherQuestion.vue'
export default {
    name:'App',
    components:{
      whouldYouRatherQestion
    },
    data() {
        return {
        ResultHeader: 'You Would Rather...',
        userChoices: [],    
        questions: [
        {
            id:0,
            question :'Would you rather live in a house shaped like a circle or a house shaped like a triangle?',
            answer1: 'Circle',
            answer2: 'Triangle'
        },
        {
            id:1,
            question :'Would you rather be able to type/text very fast or be able to read really quickly?',
            answer1: 'Type/text very fast',
            answer2: 'Read really quickly'
        },
        {
            id:2,
            question :'Would you rather ride a very big horse or a very small pony?',
            answer1: 'Big horse',
            answer2: 'Small pony'
        }
        ]


    }
},
methods: {
    userAnswers(choice) {
        // console.log(choice)
        var pieces = choice.split(","); // split choice by , to get the id for each answer 
        var index=pieces[1];
        this.$set(this.userChoices, pieces[1], pieces[0])    // will be reactive      
        // this.$set(this.userChoices, 0, ID)    // will be reactive      
      
    
    }
}
                
}
</script>

<style>
.result {
    text-align: center;
}
.answers {
    text-align: center;
    font-family: Arial, Helvetica, sans-serif;
    font-weight: 500;
    font-variant: small-caps;
    font-size: 25px;
    color: rgb(128, 86, 71);
     line-height: 1.6;
    

}

</style>


