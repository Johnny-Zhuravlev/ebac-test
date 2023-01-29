<template>
  <div class="profile">
    <div class="profile__avatar">
      <TheProfileAvatar />
    </div>
    <div class="profile__user-data">
      <TheProfilePersonalData />
      <TheProfilePassword />
    </div>
  </div>
</template>

<script>
import TheProfileAvatar from './TheProfileAvatar.vue'
import TheProfilePersonalData from './TheProfilePersonalData.vue'
import TheProfilePassword from './TheProfilePassword.vue'

export default {
  components: {
    TheProfileAvatar,
    TheProfilePersonalData,
    TheProfilePassword
  }
}
</script>

<style scoped lang="scss">
.profile {
  display: flex;
  justify-content: center;

  @media only screen and (max-width: 1280px) {
    justify-content: space-around;
  }
  @media only screen and (max-width: 1024px) {
    flex-wrap: wrap;
    justify-content: space-between;
  }
  @media only screen and (max-width: 900px) {
    justify-content: center;
  }

  &__avatar {
    max-width: 250px;
    display: flex;
    justify-content: center;
    margin-right: 80px;

    @media only screen and (max-width: 1280px) {
      margin: 0 50px 80px 0;
    }
    @media only screen and (max-width: 900px) {
      margin: 0 0 80px 0;
    }
    @media only screen and (max-width: 640px) {
      margin: 0 0 50px 0;
    }
    @media only screen and (max-width: 375px) {
      margin: 0 0 40px 0;
    }
  }

  &__user-data {
    width: 60%;
    max-width: 640px;

    @media only screen and (max-width: 900px) {
      width: 100%;
      max-width: 80%;
    }
    @media only screen and (max-width: 768px) {
      max-width: unset;
    }
  }
}
</style>
