<template>
  <div class="form-group">
    <label class="form-group__label">
      {{ label }}
      <sup v-if="hasSupTxt" class="sup-text">*</sup>
    </label>
    <slot />
  </div>
</template>

<script>
export default {
  props: {
    label: String,
    hasSupTxt: Boolean
  }
}
</script>

<style lang="scss">
.form-group {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  margin-bottom: 15px;

  @media only screen and (max-width: 480px) {
    margin-bottom: 15px;
  }

  &__inner {
    width: 100%;
  }

  &__label {
    margin-bottom: 8px;
    font-weight: 600;

    @media only screen and (max-width: 480px) {
      margin-bottom: 5px;
      font-size: 14px;
      line-height: 17px;
    }
    @media only screen and (max-width: 360px) {
      font-size: 13px;
      line-height: 15px;
    }

    .sup-text {
      color: red;
    }
  }

  &__input {
    width: 100%;
    padding: 8px 10px;
    font-size: 16px;
    line-height: 22px;
    border: 1px solid #c2c2c2;
    box-sizing: border-box;
    outline: none;
    background: #fff;
    border-radius: 8px;
    transition: all .25s linear;

    @media only screen and (max-width: 480px) {
      font-size: 14px;
      line-height: 17px;
    }
    @media only screen and (max-width: 360px) {
      font-size: 13px;
      line-height: 15px;
    }

    &:focus {
      box-shadow: 0 0 7px rgba(0,0,0, .2);
    }
  }
}
</style>
