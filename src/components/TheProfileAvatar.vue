<template>
  <form class="avatar profile-avatar">
    <div v-if="avatar" class="avatar__loader">
      <label for="avatar-loader">
        <img
          src="@/assets/img/ava.jpeg"
          class="avatar__img"
          alt="user avatar"
        />
      </label>
      <input
        id="avatar-loader"
        type="file"
        name="typeFile"
        accept="image/png, image/jpeg, image/jpg, image/webp"
      />
    </div>
    <div v-else class="avatar__loader">
      <label for="avatar-loader">
        <img
          src="@/assets/img/avatar__default.png"
          class="avatar__img"
          alt="user avatar"
        />
        <span class="avatar__txt-plug">Загрузить фото</span>
      </label>
      <input
        id="avatar-loader"
        type="file"
        name="typeFile"
        accept="image/png, image/jpeg, image/jpg, image/webp"
      />
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
  &__loader {
    display: flex;
    width: 220px;
    height: 220px;
    overflow: hidden;
    border-radius: 100%;
    position: relative;
  }

  &__img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    cursor: pointer;
  }

  &__txt-plug {
    color: #ccc;
    transform: translate(-50%, -50%);
    cursor: pointer;
    position: absolute;
    top: 50%;
    left: 50%;
  }

  input[type='file'] {
    display: none;
  }
}
</style>
