<template>
    <div ref="block" class="question--master-box" style="z-index: 20;" :style="'z-index:' + zIndex" v-if="activeQuestion">
      <img class="card--image" v-if="img" :src="img" alt="">
      <div class="question--container" >
        <p class="question-number animation-1">{{number + 1}} / 15</p>
        <div class="question">
            <div class="question-title animation-2">
              <h2>{{question}}</h2>
            </div>
            <div class="response-box animation-3">
                <div class="response" v-for="(response, index) in responses" :key="'response-' + index">
                    <div class="response--card" v-on:click="chooseResponse(response)">
                        <div class="response--card-description">{{ response.answer }}</div>
                    </div>
                </div>
            </div>
        </div>
      </div>
    </div>
</template>

<script>
import { gsap } from "gsap";

export default {
    name: 'Question',
    props: {
      heroes: Array,
      responses: Array, 
      question: String,
      clicked: Boolean,
      number: Number,
      img: String,
    },
    data(){
      return {
        activeQuestion: true
      }
    },
    computed: {
      zIndex(){
        return 100 - this.number
      }
    },
    methods:{
        chooseResponse(response){
            const pointIds = response.pointIds

            if(!pointIds.length){
                return
            }
            
            for(let i = 0; i < pointIds.length; i++){
                this.heroes.find(hero => hero.id === pointIds[i]).points++
            }

            this.activateExitAnimation()

        },
        activateExitAnimation(){
          // fix was to get the block ref and then get it's elements
          const { block } = this.$refs
          
          //element
          // const animation1 = block.getElementsByClassName("animation-1")
          // const animation2 = block.getElementsByClassName("animation-2")
          // const animation3 = block.getElementsByClassName("animation-3")

          const testImg = block.getElementsByClassName("card--image")
          const testQuestion = block.getElementsByClassName("question--container") 

          gsap.timeline().to([testImg, testQuestion], {y: -100, opacity: 0, duration:0.4})

          // gsap.timeline()
          // .to(animation1, {x: -100, opacity: 0, duration:0.6})
          // .to(animation2, {opacity: 0, duration:0.6})
          // .to(animation3, {opacity: 0, duration:0.6})

          setTimeout(() => {this.activeQuestion = false}, 400);
        },
    },
}
</script>

<style>
.question--master-box{
  height: 100vh;
  max-width: 900px;
  width: 100%;
  position: relative;
  margin: 0 auto;
}

.question--container{
  height: 400px;
  position: absolute;
  margin: auto;
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;
}

.question-number{
  text-align: left;
}
.question{
  display: flex;
}

.card--image{
  position: absolute;
  bottom: 0;
  width: 350px;
  left: 0;
  width: 400px;
}

button{
	color: white;
	border: 1px solid grey;
	font: inherit;
	cursor: pointer;
	outline: inherit;
  text-align: center;
  transition: all 0.2s;
  padding: 0;
  margin: 0;
}

button span{
  line-height:1;
}

button:hover{
  background: white;
  color: grey;
}





.question-title{
flex: 0 0 50%;
text-align: left;
font-size: 24px;
}

.response-box{
  flex: 0 0 50%;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  max-width: 900px;
  margin: 0 auto;
}

.response--card{
  max-width: 100%;
  background: white;
  transition: all 0.2s;
  border-radius: 4px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
  padding: 12px;
}

.response--card:hover{
  box-shadow: 0px 1px 20px 4px rgba(191,191,191,0.14);
  cursor: pointer;
}

.response--card-description{
  
  text-align: left;
  flex: 0 0 90%;
}

.response--card-button{
    display: flex;
  justify-content: center;
  align-items: center;
  width: 20px;
  height: 20px;
  align-self: center;
  color: red;
}
</style>