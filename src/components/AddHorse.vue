<template>
    <div>
        <label for="newHorseName">Horse Name:</label>
        <input type="text" id="newHorseName" v-model="newHorse.name">
        <label for="newHorseJockey">Jockey Name:</label>        
        <input type="text" id="newHorseJockey" v-model="newHorse.jockey">
        <button v-if="valid" v-on:click="submit">Create</button>
    </div>
</template>

<script>
export default {
  name: 'AddHorse',
  data: function() {
      return {
          newHorse: {
              name: "",
              jockey: ""
          }
      }
  },
  computed: {
      valid: function() {
          if(this.newHorse.name !== "" && this.newHorse.jockey !== "") {
            return true;
          }
          return false;        
      }
  },
  methods: {
      submit: function() {
          this.$emit('newHorseSubmission', this.newHorse)
      }
  }
}

</script>