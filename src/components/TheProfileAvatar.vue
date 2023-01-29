<template>
  <div class="avatar">
    <div class="avatar__img">
      <img src="@/assets/img/ava.jpeg" class="avatar__img" alt="user avatar" />
    </div>
    <div class="avatar__btns">
      <div class="avatar__btn btn_load">
        <label class="avatar__btn-txt" for="avatar-loader"> Загрузить фото </label>
        <input
          id="avatar-loader"
          type="file"
          name="typeFile"
          accept="image/png, image/jpeg, image/jpg, image/webp"
        />
      </div>
      <buttom class="avatar__btn btn_delete"> Удалить фото </buttom>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      avatar: '@/assets/img/ava.jpeg'
    }
  }
}
</script>

<style scoped lang="scss">
.avatar {
  &__img {
    display: flex;
    width: 220px;
    height: 220px;
    margin: 0 auto 50px;
    overflow: hidden;
    border-radius: 100%;
    position: relative;

    @media only screen and (max-width: 900px) {
      margin-bottom: 30px;
    }
    @media only screen and (max-width: 640px) {
      width: 180px;
      height: 180px;
      margin-bottom: 15px;
    }
    @media only screen and (max-width: 480px) {
      width: 150px;
      height: 150px;
    }

    img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
  }

  &__btns {
    display: flex;
  }

  &__btn {
    flex: none;
    padding: 10px;
    font-size: 14px;
    line-height: 17px;
    font-weight: 700;
    border-radius: 8px;
    cursor: pointer;
    transition: all .25s ease-out;

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

    &-txt {
      cursor: pointer;
    }

    input[type='file'] {
      display: none;
    }

    &.btn_load {
      margin-right: 10px;
      background: lightblue;

      &:hover {
        background: darken(lightblue, 10%);
      }
    }
    &.btn_delete {
      background: darkorange;

      &:hover {
        background: darken(darkorange, 5%);
      }
    }
  }
}
</style>
