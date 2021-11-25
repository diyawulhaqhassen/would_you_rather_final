<template>
  <div class="wyr">
   <h2>Would you rather</h2>
    <h3>{{question}}</h3>

    <input type="radio" v-model="choice"
           v-bind:value="wyrAnswer1"
           v-on:change="choiceMade">
    <label>{{ wyrAnswer1 }}</label>
    <input type="radio" v-model="choice"
           v-bind:value="wyrAnswer2"
           v-on:change="choiceMade">
    <label>{{ wyrAnswer2 }}</label>

  </div>
</template>

<script>
export default {
  name: 'wouldYouRather',
  props: {

    question:String,
    wyrAnswer1:String,
    wyrAnswer2:String
  },
emits:['answer-changed']
  ,data(){
    return{
      choice:''
    }
  },
  methods:{
    choiceMade(){
      this.$emit('answer-changed',this.choice)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;

}
a {
  color: #42b983;
}
.wyr{
  border: 2px black solid;
  background: #95e8a0;
  margin: 10px;
}


</style>
