<template>
  <div id="app">    
    <div class="question-container" >
      <Question 
        v-for="(question, index) in questions" :key="question.question" 
        :number="index"
        :clicked="question.clicked"
        :heroes="heroes" 
        :responses="question.responses" 
        :question="question.question"
        :img="question.img"
      />
    </div>

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
import Image1 from './assets/question-1.jpg'
import Image2 from './assets/question-2.jpg'

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
          clicked: false,
          img: Image1,
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
          question: 'What would be your preferred weapon?', 
          clicked: false,
           img: Image2,
          responses: [
            {
              answer: 'Something light and agile. You want to kill your foes swiftly.',
              pointIds: [1, 3, 6, 8,9, 12, 13, 14, 19]
            },
            {
              answer: 'The bigger the better. Crushing your enemies under a hefty weapon brings you joy.',
              pointIds: [2, 4, 17, 20, 22]
            },
            {
              answer: 'You don’t rely on a weapon. Anything that channels your inner magical powers will do enough damage.',
              pointIds: [5, 7, 11, 15, 16, 18, 21, 23]
            },
          ]
        },
      ]
    }
  },
  
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=EB+Garamond&display=swap');

body{
  background: rgb(255, 249, 233);
  margin: 0;
  padding: 0;
}
#app {
  font-family: 'EB Garamond', serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  overflow-y: hidden;
  height: 100vh;
}

p{
  margin: 0;
}

h2{
  margin: 0;
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
