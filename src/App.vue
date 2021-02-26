<template>
    
    <Greet name="Bruce" hero-name="Batman" />
    <Greet name="Clark" hero-name="Superman" />
    <Greet name="Diana" hero-name="Wonder Woman" />
    <Greet :name="name" :heroName="channel" />

</template>

<script>
import Greet from './components/Greet.vue'

  export default {
    name: 'App',
    components: {
      Greet,
    },
    data() {
      return {
        name: 'Vlad',
        channel: 'GoldenTeam'
      }
    }
  }
</script>

<style scoped>

</style>