<template>
<div>
    <textarea v-model="text" @input="handleChange"></textarea>
    <p>{{ numberOfCharacters }}/{{ maxNumberOfCharacters }}</p>
  </div>
</template>

<script>
const MAX_NUMBER_OF_CHARACTERS = 120
export default {
  data () {
    return {
      text: '',
      maxNumberOfCharacters: MAX_NUMBER_OF_CHARACTERS
    }
  },

  methods: {
    handleChange (event) {
      if (this.numberOfCharacters >= this.maxNumberOfCharacters) {
        this.text = this.text.slice(0, this.maxNumberOfCharacters)
      }
    }
  },


  computed: {
    numberOfCharacters () {
      return this.text.length
    }
  }
}
   

</script>

<style>
</style>

