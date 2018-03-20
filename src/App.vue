<template>
  <div id="app">
    <h1>Hello World</h1>
    <AddHorse v-on:newHorseSubmission="horseAddEvent"></AddHorse>
    <button v-on:click="runRace">Run the Race</button>
    <div class="horses">
      <Horse v-for="(horse, index) in horses"
        v-bind:name = "horse.name"
        v-bind:jockey = "horse.jockey"
        v-bind:key = "index"
        v-bind:number = "index">
      </Horse>
    </div>
  </div>
</template>

<script>
import Horse from './components/Horse.vue'
import AddHorse from './components/AddHorse.vue'

export default {
  name: 'app',
  components: { Horse, AddHorse },
  data: function() {
    return {
      horses: [
        { name: 'Thunder', jockey: 'Sheldon' },
        { name: 'Jandor', jockey: 'Nick' }
      ]
    }
  },
  methods: {
      horseAddEvent: function(result) {
        this.horses.push(result);
      },
      runRace: function() {
        let horse = this.horses[Math.floor(Math.random() * this.horses.length)]
        alert('Winning horse is: ' + horse.name + ', congratulations ' + horse.jockey);
      }
    }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h2 {
  color:pink;
}

.horses {

}
</style>
