<template>
  <TheProfile />
</template>

<script>
import TheProfile from '@/components/TheProfile.vue'

export default {
  name: 'App',
  components: {
    TheProfile
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #000;
  margin-top: 60px;
}
</style>
