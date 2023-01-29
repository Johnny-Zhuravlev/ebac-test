<template>
  <h3 class="title-block">{{ title }}</h3>
</template>

<script>
export default {
  props: ['title']
}
</script>

<style scoped lang="scss">
.title-block {
  margin: 0 0 20px;
  font-size: 24px;
  line-height: 28px;
  text-align: left;

  @media only screen and (max-width: 480px) {
    margin: 0 0 15px;
    font-size: 20px;
    line-height: 24px;
  }
  @media only screen and (max-width: 375px) {
    margin: 0 0 10px;
  }
}
</style>
