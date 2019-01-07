<template>
  <div id="app">
    <img src="https://www.google.com/images/branding/googlelogo/1x/googlelogo_color_272x92dp.png">
    <smart-input :goal="culprit" @inputEvent="inputEvent"></smart-input>
    <div class="buttons">
      <button>Google Search</button>
      <button>I'm feeling lucky</button>
    </div>
    <key-wizard :needs-pressed="whatsLeft"></key-wizard>

  </div>
</template>

<script>
import smartInput from './components/smartInput.vue'
import keyWizard from './components/keyWizard.vue'

export default {
  name: 'app',
  components: {
    smartInput,
    keyWizard
  },
  computed: {
    whatsLeft: function(){
      var resolved = 0;
      this.currentStatus.split('').forEach((letter, index)=>{
        if(letter == this.culprit[index]){
          resolved++;
        }
      });
      return this.culprit.slice(resolved);
    }
  },
  data(){
    return{
      culprit: 'meow', 
      currentStatus: ''
    }
  },
  methods: {
    inputEvent: function(data){
      this.currentStatus = data;
    },
    getCulprit: function(){
      var urlParams = new URLSearchParams(window.location.search);
      console.log(urlParams);
    }
  },
  created: function(){

  }
}
</script>

<style lang="scss">
#app {
  width: 100%;
  height: 70vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  .buttons{
    button{
      height: 36px;
      background-color: #f2f2f2;
      border: 1px solid #f2f2f2;
      border-radius: 2px;
      color: #757575;
      cursor: default;
      font-family: arial,sans-serif;
      font-size: 13px;
      font-weight: bold;
      margin: 11px 4px;
      min-width: 54px;
      padding: 0 16px;
      text-align: center;
    }
  }
}
</style>
