<template>
  <intro />
  <router-view/>
</template>
<script>
import Intro from '@/components/Intro'
export default {
    components: {
    Intro
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
body{
  margin: 0;
}
</style>
