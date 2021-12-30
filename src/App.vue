<template>
  <div id="app">
    <!-- <Question text="Welcome to Your Vue.js App"/> -->
    <h2>{{question}}</h2>
    <div class="response-box">
      <div class="response" v-for="(response, index) in responses" :key="'response-' + index">
        <div class="response--card">
          <div class="response--card-art"></div>
          <div class="response--card-description">{{ response.answer }}</div>
        </div>
      </div>
    </div>
    
  </div>
</template>

<script>
// import Question from './components/Question.vue'

      // result: [Bravo, Dorinthea, Benji, Prism, Bolytn, Lexi, Oldhim, Valda],
       // result: [Katsu, Ira]
        // result: [Viserai, Dash, Kano, DataDoll, Chane, Levia, Shiyana]
        // result: [Azalea, Kavdaen(2), Kassai]

export default { 
  name: 'App',
  // components: {
  //   Question
  // },
  data(){
    return {
    question: 'Which scenario is most likely to spur you into action?',
    heroes: [
      {id: 1, name: 'Bravo', points: 0},
      {id: 2, name: 'Dorinthea', points: 0}
    ],
    responses: [
      {
        answer: 'A nearby town has many innocent lives in danger. Only you know how to stop the disaster.',
        heroIndex: [2] //the point we want to increase
      },
      {
        answer: 'You heard your sibling has been imprisoned by a distant ruler.',
      },
      {
        answer: 'A reliable source has told you of a unique artifact. You know this artifact can enhance your abilities beyond comprehension.'
      },
      {
        answer: 'You have a tip-off for a hidden treasure that could make you incredibly wealthy.',
      },
    ]
    }
  },
  // computed: {
  //   getHero(){
  //     return 
  //   }
  // }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=EB+Garamond&display=swap');

body{
  background: rgb(255, 249, 233);
  
}
#app {
  font-family: 'EB Garamond', serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  
}

button{
  display: block;
}

.response-box{
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  max-width: 900px;
  margin: 0 auto;
}

.response--card{
  min-height: 400px;
  max-width: 180px;
  background: white;
  padding: 15px;
  transition: all 0.2s;
  border-radius: 4px;
}

.response--card:hover{
  box-shadow: 0px 1px 20px 4px rgba(191,191,191,0.14);
  cursor: pointer;
}

.response--card-art{
  min-height: 300px;
  
}
</style>
