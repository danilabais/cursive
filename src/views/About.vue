<template>
  <div>
    <h1>Тестирование</h1>
    <h2>Количество предложений в тексте = {{range}}</h2>
    <input v-model.number="range" type="range" class="form-range" min="1" max="10" id="customRange2">
    <button v-on:click="fetchArticle($event)" class="btn btn-primary" type="button">Начать тестирование</button>
    <p class="text" ref="lol" v-html="this.response"></p>
    <h1 >Длинна текста: {{text.length}}</h1>
    <h1 >Введено текста: {{Math.floor(i/text.length*100)}}%</h1>
    <h1 >Правильность: {{Math.floor(Math.abs(mistakes/text.length*100-100))}}</h1>
  </div>
</template>

<script>
import axios from 'axios'

export default {
 data() {
    return { 
      range:1,
      isStart:false,
      response:null,
      text:[],
      i:0,
      mistakes:0,
     }
  },
  methods: {
     async fetchArticle() {
       const response = await axios.get(`https://fish-text.ru/get?format=text&number=${this.range}`) 
      let a =response.data.text
      a=a.split('')
      this.text=response.data.text
      for (let i in a) {    
          a[i]=`<span>${a[i]}</span>`
      }
      a=a.join('')
      this.response=a
    },
    lol(e){
      if (e.key!=='Shift') {
       
        if (this.text[this.i]==e.key) {
          this.$refs.lol.childNodes[this.i].classList.add('true')
          this.i++
        }else {
          this.mistakes++
          this.$refs.lol.childNodes[this.i].classList.add('false')
        }
      }
      
      
    }
    
  
},
    mounted(){
      window.addEventListener('keydown',(e)=>this.lol(e))

    }
}
</script>

<style>
  p {
    max-width: 70vw;
  }
    .false {
      color:red;
    }
  .true {
    color:green;
  }
  .text {
    font-size: 4rem;
  }
</style>