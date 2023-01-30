<template>
  <div class="profile">
    <div class="profile__form user-data-form">
      <div class="profile__avatar">
        <TheProfileAvatar />
      </div>
      <div class="profile__user-data">
        <TheProfilePersonalData />
      </div>
    </div>

    <div class="profile__form form_passwords">
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
  width: 100%;
  max-width: 970px;
  margin: 0 auto;

  &__form {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    margin: 0 0 50px;

    @media only screen and (max-width: 1280px) {
      justify-content: space-between;
    }
    @media only screen and (max-width: 1024px) {
      flex-wrap: wrap;
      justify-content: space-between;
    }
    @media only screen and (max-width: 900px) {
      justify-content: center;
    }
    @media only screen and (max-width: 480px) {
      margin: 0 0 35px;
    }

    &.form_passwords {
      width: 65%;
      display: flex;
      justify-content: flex-end;
      margin-left: auto;

      @media only screen and (max-width: 1024px) {
        width: 60%;
      }
      @media only screen and (max-width: 900px) {
        width: 80%;
        margin: 0 auto;
      }
      @media only screen and (max-width: 640px) {
        width: 100%;
        margin: 0;
      }
    }
  }

  &__avatar {
    max-width: 260px;
    display: flex;
    justify-content: center;
    margin-right: 80px;

    @media only screen and (max-width: 1280px) {
      margin: 0 40px 80px 0;
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
    width: 65%;

    @media only screen and (max-width: 1024px) {
      width: 60%;
    }
    @media only screen and (max-width: 900px) {
      width: 80%;
    }
    @media only screen and (max-width: 640px) {
      width: 100%;
    }
  }
}
</style>
