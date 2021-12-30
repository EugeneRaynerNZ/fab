<template>
    <div class="question">
        <h2>{{question}}</h2>
        <div class="response-box">
            <div class="response" v-for="(response, index) in responses" :key="'response-' + index">
                <div class="response--card" v-on:click="clickResponse(response)">
                    <div class="response--card-art">
                        <span style="font-size: 12px">Card art here</span>
                    </div>
                    <div class="response--card-description">{{ response.answer }}</div>
                    <button class="response--card-button">Select</button>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Question',
    props: ['heroes', 'responses', 'question'],
    methods:{
        clickResponse(response){
            const pointIds = response.pointIds

            if(!pointIds.length){
                return
            }
            
            for(let i = 0; i < pointIds.length; i++){
                this.heroes.find(hero => hero.id === pointIds[i]).points++
            }

        }
    }
}
</script>

<style>
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
</style>