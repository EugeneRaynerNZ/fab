<template>
  <div id="app">    
    <Question :heroes="heroes"/>

    <div>
      <h4>For development purposes only</h4>
      <div class="hero--points">
        <div class="hero--points-hero" v-for="hero in heroes" :key="hero.id">
          <p><strong>{{hero.name}}</strong></p>
          <p>Points: <strong>{{hero.points}}</strong></p>
        </div>
      </div>
    </div>
    
  </div>
</template>

<script>
import Question from './components/Question.vue'

export default { 
  name: 'App',
  components: {
    Question
  },
  data(){
    return {
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
    }
  },
  
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
