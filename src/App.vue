<template>
  <div id="app">
    <h1>Would You Rather......
    </h1>
    <would-you-rather
        v-for="question in questions"
        v-bind:question="question.wyrQuestion" v-bind:key="question"
        v-bind:wyrAnswer1="question.wyrAnswer1"
        v-bind:wyrAnswer2="question.wyrAnswer2"
        v-on:answer-changed="answerChanged"></would-you-rather>
    <div> You would Rather...
      <ul class='userChoice' >
        <li v-for="answer in userSelectionMessage"
        v-bind:key="answer">
          {{answer}}

        </li>
      </ul >

    </div>
  </div>
</template>

<script>
import wouldYouRather from './components/wouldYouRather.vue'

export default {
  name: 'App',
  components: {
    // eslint-disable-next-line vue/no-unused-components
    wouldYouRather
  },
  // props:{
  //   questions:Array,
  //
  // },
  data(){
    return{
      questions:[
        {id:0,
          wyrQuestion:'would you rather live in a house shaped like a circle or a house shaped like a triangle?',
          wyrAnswer1:'Circle house',
          wyrAnswer2:'Triangle House',

        },{id:1,
          wyrQuestion:'Would you rather eat smores or cupcakes?',
          wyrAnswer1:'Smore',
          wyrAnswer2:'Cupcake',

        },{id:2,
          wyrQuestion:'Would you rather be able to talk to dogs or cats?',
          wyrAnswer1:'Dog',
          wyrAnswer2:'Cat',

        }
      ],

      userSelectionMessage:[]
    }
  },
  methods:{
    answerChanged(choice) {
      if (choice===this.questions[0].wyrAnswer1||choice===this.questions[0].wyrAnswer2){
        this.userSelectionMessage[0]=`Thanks! you chose ${choice}`
      }
      if (choice===this.questions[1].wyrAnswer1||choice===this.questions[1].wyrAnswer2){
        this.userSelectionMessage[1]=`Thanks! you chose ${choice}`
      }
      if (choice===this.questions[2].wyrAnswer1||choice===this.questions[2].wyrAnswer2){
        this.userSelectionMessage[2]=`Thanks! you chose ${choice}`
      }
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background: #ffffff;
  border: black solid 2px;

}
</style>
