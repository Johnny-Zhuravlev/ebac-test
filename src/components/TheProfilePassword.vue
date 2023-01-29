<template>
  <div class="passwords">
    <v-title-block title="Смена пароля" />
    <v-form-group label="Текущий пароль" has-sup-txt>
      <InputPassword placeholder="Введите текущий пароль" />
    </v-form-group>
    <v-form-group label="Новый пароль" has-sup-txt>
      <InputPassword placeholder="Введите новый пароль" />
    </v-form-group>
  </div>
</template>

<script>
import vTitleBlock from './ProfileTitleBlock.vue'
import vFormGroup from './UI/FormGroup.vue'
import InputPassword from './UI/InputPassword.vue'

export default {
  components: {
    vTitleBlock,
    vFormGroup,
    InputPassword
  },
  data () {
    return {}
  }
}
</script>

<style scoped lang="scss">
.passwords {
  margin: 50px 0;

  @media only screen and (max-width: 480px) {
    margin: 35px 0;
  }
}
</style>
