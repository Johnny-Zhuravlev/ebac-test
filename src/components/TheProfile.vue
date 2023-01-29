<template>
  <div class="profile">
    <form class="profile__form">
      <div class="profile__avatar">
        <TheProfileAvatar />
      </div>
      <div class="profile__user-data">
        <TheProfilePersonalData />
        <TheProfilePassword />
      </div>

      <div class="profile__form-footer">
        <button class="profile__form-btn">Сохранить</button>
      </div>
    </form>
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
  &__form {
    display: flex;
    flex-wrap: wrap;
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

    &-footer {
      width: 100%;
      max-width: 970px;
      display: flex;
      justify-content: flex-end;
    }

    &-btn {
      flex: none;
      font-size: 16px;
      line-height: 20px;
      color: #fff;
      background: #237CE7;

      &:hover {
        background: darken(#237CE7, 10%);
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
