<template>
  <div class="profile">
    <div class="profile__avatar">
      <TheProfileAvatar />
    </div>
  </div>
</template>

<script>
import TheProfileAvatar from './TheProfileAvatar.vue'
export default {
  components: {
    TheProfileAvatar
  }
}
</script>

<style scoped lang="scss">
.profile {
  display: flex;
  flex-wrap: wrap;

  &__avatar {
    width: 25%;
    display: flex;
    justify-content: center;
  }
}
</style>
