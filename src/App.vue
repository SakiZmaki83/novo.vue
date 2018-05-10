<template>
  <div id="app">
    <!-- <twitter-input />  -->
    <!-- <password-input /> -->
    <div>
      {{ name | allCaps | lowercase | join(name, lastName) }}
      <!-- {{ lastName | allCaps }} -->
    </div>
    <app-test>
      <div slot-scope="slotProps">
        {{ slotProps.color }}
        {{ slotProps.lastName }}
      </div>
    </app-test>
  </div>
</template>

<script>
   
import TwitterInput from './components/TwitterInput.vue'
import PasswordInput from './components/PasswordInput.vue'
import AppTest from './components/AppTest.vue'

export default {
  name: 'app',
  components: {
   TwitterInput,
   PasswordInput,
   AppTest,
  },
  data(){
    return{
      name: 'Sandra',
      lastName: 'Micevic'
    }
  },

  filters: {
    allCaps (value) {
      if (!value) {
        return ''
      }
      return value.toString().toUpperCase()
    },
    lowercase (value) {
      if (!value) {
        return ''
      }
      return value.toString().toLowerCase()
    }, 
    join (value, arg1, arg2) {
      return `${value}+${arg1}+${arg2}`
    }
  }
}
</script>

