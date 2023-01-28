<template>
  <form class="avatar">
    <div class="avatar__img">
      <img src="@/assets/img/ava.jpeg" class="avatar__img" alt="user avatar" />
    </div>
    <div class="avatar__btns">
      <div class="avatar__btn btn_load">
        <label for="avatar-loader"> Загрузить фото </label>
        <input
          id="avatar-loader"
          type="file"
          name="typeFile"
          accept="image/png, image/jpeg, image/jpg, image/webp"
        />
      </div>
      <buttom class="avatar__btn btn_delete"> Удалить фото </buttom>
    </div>
  </form>
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
    margin-bottom: 50px;
    overflow: hidden;
    border-radius: 100%;
    position: relative;

    img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      cursor: pointer;
    }
  }

  &__btns {
    display: flex;
  }

  &__btn {
    padding: 10px;
    font-size: 14px;
    line-height: 17px;
    font-weight: 700;
    border-radius: 8px;

    input[type='file'] {
      display: none;
    }

    &.btn_load {
      margin-right: 10px;
      background: lightblue;
    }
    &.btn_delete {
      background: darkorange;
    }
  }
}
</style>
