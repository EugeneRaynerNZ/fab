<template>
  <div id="app">
    <!-- <Question text="Welcome to Your Vue.js App"/> -->
    <h2>{{question}}</h2>
    <div class="response-box">
      <div class="response" v-for="(response, index) in responses" :key="'response-' + index">
        <div class="response--card" v-on:click="clickResponse(response)">
          <div class="response--card-art"><span style="font-size: 12px">Card art here</span></div>
          <div class="response--card-description">{{ response.answer }}</div>
          <button class="response--card-button">Select</button>
        </div>
      </div>
    </div>

    <div>
      <h4>For development purposes only</h4>
      <div class="hero--points">
        <div class="hero--points-hero" v-for="hero in heroes" :key="hero.id">
          <p><strong>{{hero.name}}</strong></p>
          <p>Points: {{hero.points}}</p>
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
      {id: 1, name: 'Katsu', points: 0},
      {id: 2, name: 'Bravo', points: 0},
      {id: 3, name: 'Dorinthea', points: 0},
      {id: 4, name: 'Rhinar', points: 0},
      {id: 5, name: 'Viserai', points: 0},
      {id: 6, name: 'Dash', points: 0},
      {id: 7, name: 'Kano', points: 0},
      {id: 8, name: 'Azalea', points: 0},
      {id: 9, name: 'Benji', points: 0},
      {id: 10, name: 'Kavdaen', points: 0},
      {id: 11, name: 'Data Doll', points: 0},
      {id: 12, name: 'Ira', points: 0},
      {id: 13, name: 'Kayo', points: 0},
      {id: 14, name: 'Kassai', points: 0},
      {id: 15, name: 'Chane', points: 0},
      {id: 16, name: 'Prism', points: 0},
      {id: 17, name: 'Boltyn', points: 0},
      {id: 18, name: 'Levia', points: 0},
      {id: 19, name: 'Lexi', points: 0},
      {id: 20, name: 'Oldhim', points: 0},
      {id: 21, name: 'Briar', points: 0},
      {id: 22, name: 'Valda', points: 0},
      {id: 23, name: 'Shiyana', points: 0},
    ],
    responses: [
      {
        answer: 'A nearby town has many innocent lives in danger. Only you know how to stop the disaster.',
        pointIds: [1, 20]
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
  methods:{
    clickResponse(response){
      const pointIds = response.pointIds
      //for each pointIds, loop through heroes array and find the same id
      

      for(let i = 0; i < pointIds.length; i++){
        this.heroes.find(hero => hero.id === pointIds[i]).points++

      }

    }
  }
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
  background: grey;
	color: white;
	border: 1px solid grey;
	padding: 12px;
	font: inherit;
	cursor: pointer;
	outline: inherit;
  width: 100%;
  text-align: center;
  transition: all 0.2s;
}

button:hover{
  background: white;
  color: grey;
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
  max-width: 200px;
  background: white;
  transition: all 0.2s;
  border-radius: 4px;
}

.response--card:hover{
  box-shadow: 0px 1px 20px 4px rgba(191,191,191,0.14);
  cursor: pointer;
}

.response--card-art{
  min-height: 300px;
  display: flex;
  justify-content: center;
  align-items: center;
  border: 1px solid rgba(191,191,191,0.4);
}

.response--card-art span{
  padding: 0 10px;
}

.response--card-description{
  padding: 12px;
  min-height: 105px;
}

/* For dev purposes */
.hero--points{
  border: 1px solid blue;
  display: flex;
  flex-wrap: wrap;
}

.hero--points-hero{
  padding: 12px;
  border: 1px solid red;
}

.hero--points-hero p{
  margin: 0;
}
</style>
