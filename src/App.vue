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

button {
  padding: 10px;
  font-size: 14px;
  line-height: 17px;
  font-weight: 700;
  border: 0;
  outline: none;
  border-radius: 8px;
  cursor: pointer;
  transition: all 0.25s ease-out;
}

.container {
  max-width: 1400px;
  margin: 0 auto;
  padding: 80px;

  @media only screen and (max-width: 768px) {
    padding: calc(80 * 100% / 768);
  }
  @media only screen and (max-width: 480px) {
    padding: 40px calc(40 * 100% / 480);;
  }
}
</style>
