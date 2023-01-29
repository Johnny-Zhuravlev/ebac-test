<template>
  <div class="user-data">
    <v-title-block title="Личные данные" />
    <v-form-group label="ФИО" has-sup-txt>
      <input
        class="form-group__input"
        type="text"
        placeholder="Петрова Алефтина Валерьевна"
        required
      />
    </v-form-group>
    <v-form-group label="Дата рождения">
      <input
        v-maska
        data-maska="##.##.####"
        class="form-group__input"
        type="text"
        placeholder="01.01.2001"
      />
    </v-form-group>
    <v-form-group label="E-mail" has-sup-txt>
      <input
        class="form-group__input"
        type="text"
        placeholder="superUser223@gmail.com"
        required
      />
    </v-form-group>
    <v-form-group label="Город">
      <input
        class="form-group__input"
        type="text"
        placeholder="Торжок"
      />
    </v-form-group>
    <v-form-group label="Телефон">
      <input
        v-maska
        data-maska="+7 (###) ###-##-##"
        class="form-group__input"
        type="text"
        placeholder="+7 (999) 333-99-11"
      />
    </v-form-group>
    <v-form-group label="Владение языками">
      <div class="form-group__inner">
        <div class="output">{{ lang.label }}</div>
        <Multiselect v-model="value" v-bind="lang" :options="lang.options" />
      </div>
    </v-form-group>
  </div>
</template>

<script>
import vTitleBlock from './ProfileTitleBlock.vue'
import vFormGroup from './UI/FormGroup.vue'
import Multiselect from '@vueform/multiselect'
import '@/assets/sass/libs/multiselect.scss'

export default {
  components: {
    vTitleBlock,
    vFormGroup,
    Multiselect
  },
  data () {
    return {
      lang: {
        mode: 'tags',
        closeOnSelect: false,
        value: ['russian'],
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
      },
      searchable: true,
      createOption: true
    }
  }
}
</script>

<style scoped lang="scss"></style>
