<template>
  <div id="app">    
    <Question 
      v-for="question in questions" 
      :key="question.question" 
      :heroes="heroes" 
      :responses="question.responses" 
      :question="question.question"
    />

    <div class="hero--points">
      <div class="hero--points-hero" v-for="hero in heroes" :key="hero.id">
        <p><strong>{{hero.name}}</strong></p>
        <p>Points: <strong>{{hero.points}}</strong></p>
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
      questions: [
        {
          question: 'Which scenario is most likely to spur you into action?', 
          responses: [
            {
              answer: 'A nearby town has many innocent lives in danger. Only you know how to stop the disaster.',
              pointIds: [2, 3, 9, 16, 17, 19, 20, 22]
            },
            {
              answer: 'You heard your sibling has been imprisoned by a distant ruler.',
              pointIds: [1, 12]
            },
            {
              answer: 'A reliable source has told you of a unique artifact. You know this artifact can enhance your abilities beyond comprehension.',
              pointIds: [5, 6, 7, 11, 15, 18, 23]
            },
            {
              answer: 'You have a tip-off for a hidden treasure that could make you incredibly wealthy.',
              pointIds: [8, 14, 10, 10]
            },
          ]
        },
        {
          question: 'Which scenario is most likely to spur you into action?2312', 
          responses: [
            {
              answer: 'A nearby town has many innocent lives in danger. Only you know how to stop the disaster.',
              pointIds: [2, 3, 9, 16, 17, 19, 20, 22]
            },
            {
              answer: 'You heard your sibling has been imprisoned by a distant ruler.',
              pointIds: [1, 12]
            },
            {
              answer: 'A reliable source has told you of a unique artifact. You know this artifact can enhance your abilities beyond comprehension.',
              pointIds: [5, 6, 7, 11, 15, 18, 23]
            },
            {
              answer: 'You have a tip-off for a hidden treasure that could make you incredibly wealthy.',
              pointIds: [8, 14, 10, 10]
            },
          ]
        }
      ]
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
  position: fixed;
  top: 0;
  left: 0;
  height: 100vh;
  width: 200px;
}

.hero--points-hero{
  padding: 12px;
  border: 1px solid red;
}

.hero--points-hero p{
  margin: 0;
}
</style>
