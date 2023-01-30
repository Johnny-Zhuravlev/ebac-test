<template>
  <Form
    class="passwords"
    @submit="onSubmitPasswords"
    :validation-schema="schema"
    v-slot="{ errors }"
  >
    <v-title-block title="Смена пароля" />
    <v-form-group label="Текущий пароль" has-sup-txt>
      <div class="form-control">
        <div class="form-control__inner">
          <Field
            class="form-group__input"
            :class="{ 'is-invalid': errors.currentPassword }"
            name="currentPassword"
            :type="currentPasswordType"
            placeholder="Введите текущий пароль"
            ref="currentPassword"
          />
          <icon-eye-closed
            v-show="currentPasswordType === 'password'"
            class="icon-eye-closed"
            @click.self="currentPasswordType = 'text'"
          />
          <icon-eye-opened
            v-show="currentPasswordType === 'text'"
            class="icon-eye-opened"
            @click.self="currentPasswordType = 'password'"
          />
        </div>
        <div v-show="errors.currentPassword" class="error">
          {{ errors.currentPassword }}
        </div>
      </div>
    </v-form-group>
    <v-form-group label="Новый пароль" has-sup-txt>
      <div class="form-control">
        <div class="form-control__inner">
          <Field
            class="form-group__input"
            :class="{ 'is-invalid': errors.newPassword }"
            name="newPassword"
            :type="newPasswordType"
            placeholder="Введите новый пароль"
            ref="newPassword"
          />
          <icon-eye-closed
            v-show="newPasswordType === 'password'"
            class="icon-eye-closed"
            @click="newPasswordType = 'text'"
          />
          <icon-eye-opened
            v-show="newPasswordType === 'text'"
            class="icon-eye-opened"
            @click="newPasswordType = 'password'"
          />
        </div>
        <div v-show="errors.newPassword" class="error">
          {{ errors.newPassword }}
        </div>
      </div>
    </v-form-group>
    <v-form-group label="Повторите новый пароль" has-sup-txt>
      <div class="form-control">
        <div class="form-control__inner">
          <Field
            class="form-group__input"
            :class="{ 'is-invalid': errors.newPasswordRepeated }"
            name="newPasswordRepeated"
            :type="newPasswordRepeatedType"
            placeholder="Повторите новый пароль"
            ref="newPasswordRepeated"
          />
          <icon-eye-closed
            v-show="newPasswordRepeatedType === 'password'"
            class="icon-eye-closed"
            @click="newPasswordRepeatedType = 'text'"
          />
          <icon-eye-opened
            v-show="newPasswordRepeatedType === 'text'"
            class="icon-eye-opened"
            @click="newPasswordRepeatedType = 'password'"
          />
        </div>
        <div v-show="errors.newPasswordRepeated" class="error">
          {{ errors.newPasswordRepeated }}
        </div>
      </div>
    </v-form-group>

    <BaseBtn text="Сохранить" />
  </Form>
</template>

<script>
import { Form, Field } from 'vee-validate'
import vTitleBlock from './ProfileTitleBlock.vue'
import vFormGroup from './UI/FormGroup.vue'
import IconEyeClosed from './UI/icons/IconEyeClosed.vue'
import IconEyeOpened from './UI/icons/IconEyeOpened.vue'
import BaseBtn from './UI/BaseBtn.vue'
import * as Yup from 'yup'

export default {
  components: {
    Form,
    vTitleBlock,
    vFormGroup,
    Field,
    IconEyeClosed,
    IconEyeOpened,
    BaseBtn
  },
  data () {
    const currentPasswordType = 'password'
    const newPasswordType = 'password'
    const newPasswordRepeatedType = 'password'
    const schema = Yup.object().shape({
      currentPassword: Yup.string()
        .required('Введите актуальный пароль')
        .min(6, 'Пароль должен быть более 8 символов')
        .max(30, 'Пароль должно быть более 30 символов'),
      newPassword: Yup.string()
        .required('Введите новый пароль')
        .min(6, 'Пароль должен быть более 8 символов')
        .max(30, 'Пароль должно быть более 30 символов'),
      newPasswordRepeated: Yup.string()
        .required('Повторите новый пароль')
        .min(6, 'Пароль должен быть более 8 символов')
        .max(30, 'Пароль должно быть более 30 символов')
        .oneOf([Yup.ref('newPassword'), null], 'Пароли должны совпадать')
    })

    return {
      currentPasswordType,
      newPasswordType,
      newPasswordRepeatedType,
      schema
    }
  },
  methods: {
    onSubmitPasswords (values) {
      // display form values on success
      alert('SUCCESS!! :-)\n\n' + JSON.stringify(values, null, 4))
    }
  }
}
</script>

<style scoped lang="scss">
.passwords {
  width: 100%;
}

.form-control {
  width: 100%;

  &__inner {
    position: relative;
  }
}

.icon-eye-closed,
.icon-eye-opened {
  position: absolute;
  top: 50%;
  right: 10px;
  cursor: pointer;
  transform: translateY(-50%);

  @media only screen and (max-width: 480px) {
    width: 20px;
  }
}

.error {
  margin-top: 5px;
  font-size: 12px;
  line-height: 17px;
  font-weight: 600;
  color: red;
  letter-spacing: .15px;
  text-align: left;
}
</style>
