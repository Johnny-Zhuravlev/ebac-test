<template>
  <button class="btn">{{ text }}</button>
</template>

<script>
export default {
  props: ['text']
}

</script>

<style scoped lang="scss">
.btn {
  display: block;
  margin-left: auto;
  font-size: 16px;
  line-height: 20px;
  color: #fff;
  background: #237ce7;

  &:hover {
    background: darken(#237ce7, 10%);
  }

  @media only screen and (max-width: 480px) {
    font-size: 13px;
  }
  @media only screen and (max-width: 375px) {
    padding: 8px;
  }
  @media only screen and (max-width: 320px) {
    font-size: 12px;
    line-height: 16px;
  }
}
</style>
