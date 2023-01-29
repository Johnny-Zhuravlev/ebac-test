<template>
  <div class="form-control">
    <input
      class="form-group__input"
      :type="type"
      :placeholder="placeholder"
    />
    <icon-eye-closed
      v-show="type === 'password'"
      class="icon-eye-closed"
      @click="type = 'text'"
    />
    <icon-eye-opened
      v-show="type === 'text'"
      class="icon-eye-opened"
      @click="type = 'password'"
    />
  </div>
</template>

<script>
import IconEyeClosed from './icons/IconEyeClosed.vue'
import IconEyeOpened from './icons/IconEyeOpened.vue'

export default {
  components: {
    IconEyeClosed,
    IconEyeOpened
  },
  props: {
    placeholder: String
  },
  data () {
    return {
      type: 'password'
    }
  }
}
</script>

<style scoped lang="scss">
.form-control {
  width: 100%;
  position: relative;
}

.icon-eye-closed,
.icon-eye-opened {
  position: absolute;
  top: 50%;
  right: 10px;
  transform: translateY(-50%);

  @media only screen and (max-width: 480px) {
    width: 20px;
  }
}
</style>
