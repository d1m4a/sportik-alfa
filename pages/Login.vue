<template lang="pug">
  section.login__wrapper
    b-container
      b-row
        b-col
          h2.header__places Войти в админку
          b-form(@submit="onSubmit" @reset="onReset" v-if="show")
            b-form-group(
              id="input-group-1"
              label="Введите email адрес:"
              label-for="input-1"
            )
              b-form-input(
                id="input-1"
                v-model="form.email"
                type="email"
                required
                placeholder="Введите email"
              )
            b-form-group(
              id="input-group-2"
              label="Пароль:"
              label-for="input-2"
            )
              b-form-input(
                id="input-2"
                v-model="form.password"
                type="password"
                required
                placeholder="Введите пароль"
              )
            .button__group.text-center
              b-button(type="submit" variant="outline-dark") Войти

</template>

<script>
  export default {
  data() {
      return {
        form: {
          email: '',
          password: '',
        },
        show: true
      }
    },
  methods: {
      onSubmit(evt) {
        evt.preventDefault()
        console.log(JSON.stringify(this.form))
      },
      onReset(evt) {
        evt.preventDefault()
        // Сбрасываем значения формы
        this.form.email = ''
        this.form.password = ''

        // Trick to reset/clear native browser form validation state
        this.show = false
        this.$nextTick(() => {
          this.show = true
        })
      }
    }
  }
</script>

<style lang="scss">
  .login__wrapper {
    max-width: 500px;
    margin: 0 auto;
    width: 100%;
  }
</style>