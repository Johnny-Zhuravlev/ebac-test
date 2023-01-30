<template>
  <Form
    class="user-data"
    @submit="onSubmitUserData"
    :validation-schema="schema"
    v-slot="{ errors }"
  >
    <v-title-block title="Личные данные" />
    <v-form-group label="ФИО" has-sup-txt>
      <Field
        class="form-group__input"
        :class="{ 'is-invalid': errors.fullname }"
        v-model="userData.fullname"
        name="fullname"
        type="text"
        placeholder="Петрова Алефтина Валерьевна"
      />
      <div v-show="errors.fullname" class="error">{{errors.fullname}}</div>
    </v-form-group>
    <v-form-group label="Дата рождения">
      <Field
        v-maska
        data-maska="##.##.####"
        class="form-group__input"
        :class="{ 'is-invalid': errors.birthdate }"
        v-model="userData.birthdate"
        name="birthdate"
        type="text"
        placeholder="01.01.2001"
      />
      <div v-show="errors.birthdate" class="error">{{errors.birthdate}}</div>
    </v-form-group>
    <v-form-group label="E-mail" has-sup-txt>
      <Field
        class="form-group__input"
        :class="{ 'is-invalid': errors.email }"
        v-model="userData.email"
        name="email"
        type="text"
        placeholder="superUser223@gmail.com"
      />
      <div v-show="errors.email" class="error">{{errors.email}}</div>
    </v-form-group>
    <v-form-group label="Город">
      <Field
        class="form-group__input"
        v-model="userData.city"
        name="city"
        type="text"
        placeholder="Торжок"
      />
    </v-form-group>
    <v-form-group label="Телефон">
      <Field
        v-maska
        data-maska="+7 (###) ###-##-##"
        class="form-group__input"
        v-model="userData.tel"
        name="tel"
        type="text"
        placeholder="+7 (999) 333-99-11"
      />
    </v-form-group>
    <v-form-group label="Владение языками">
      <div class="form-group__inner">
        <div class="output">{{ lang.label }}</div>
        <Multiselect
          v-model="userData.langs[0]"
          v-bind="lang"
          :options="lang.options"
        />
      </div>
    </v-form-group>

    <BaseBtn text="Сохранить" />
  </Form>
</template>

<script>
import vTitleBlock from './ProfileTitleBlock.vue'
import vFormGroup from './UI/FormGroup.vue'
import { Form, Field } from 'vee-validate'
import Multiselect from '@vueform/multiselect'
import '@/assets/sass/libs/multiselect.scss'
import BaseBtn from './UI/BaseBtn.vue'
import * as Yup from 'yup'

export default {
  components: {
    Form,
    vTitleBlock,
    vFormGroup,
    Field,
    Multiselect,
    BaseBtn
  },
  data () {
    const userData = {
      fullname: '',
      birthdate: '',
      email: '',
      city: '',
      tel: '',
      langs: []
    }
    const lang = {
      mode: 'tags',
      closeOnSelect: false,
      options: [
        { value: 'russian', label: 'Русский' },
        { value: 'english', label: 'Английский' },
        { value: 'spanish', label: 'Испанский' },
        { value: 'deutsch', label: 'Немецкий' },
        { value: 'italian', label: 'Итальянский' },
        { value: 'chinese', label: 'Китайский' },
        { value: 'japanese', label: 'Японский' },
        { value: 'hindi', label: 'Индийский' }
      ]
    }
    const searchable = true
    const createOption = true
    const schema = Yup.object().shape({
      fullname: Yup.string()
        .required('ФИО обязательно')
        .min(6, 'ФИО должно быть от 6 до 40 символов')
        .max(40, 'ФИО должно быть от 6 до 40 символов'),
      birthdate: Yup.string()
        .required('Date of Birth is required')
        .matches(/^((((0?[1-9].(0?[1-9]|1[0-2]))|([12][0-9].((0?[13-9])|1[0-2]))|(((1[0-9])|(2[0-8])).0?2)|(30.((0?[13-9])|1[0-2]))|(31.((0?[13578])|10|12))).[0-9]{4})|(29.0?2.(([0-9]{2}((0[48])|([2468][048])|([13579][26])))|((([02468][048])|([13579][26]))00))))$/, 'Дата рождения введена некорректно'),
      email: Yup.string()
        .required('Email обязателен')
        .email('Email введен некорректно')
    })

    return {
      userData,
      lang,
      searchable,
      createOption,
      schema
    }
  },
  methods: {
    onSubmitUserData (values) {
      alert('SUCCESS!! :-)\n\n' + JSON.stringify(values, null))
    }
  }
}
</script>

<style scoped lang="scss">
.error {
  margin-top: 5px;
  font-size: 12px;
  line-height: 17px;
  font-weight: 600;
  color: red;
  letter-spacing: .15px;
}
</style>
