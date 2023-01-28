<template>
  <div class="container">
    <TheProfile />
  </div>
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
body {
  margin: 0;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #000;
}

.container {
  max-width: 1680px;
  margin: 0 auto;
  padding: 80px 5%;
}
</style>
