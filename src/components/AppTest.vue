<template>
  <div>
      <slot :color="color" :lastName="lastName"></slot>
    
  </div>
</template>

<script>


export default {
    data(){
        return {
            color: 'Blue',
            lastName: 'Bla'
        }
    }

}
</script>

