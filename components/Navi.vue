<template lang="pug">
  header.mb50
    b-navbar(toggleable="lg" type="dark" variant="dark")
      b-navbar-brand(to="/") Sportik
        span.highlighted alfa
      b-navbar-toggle(target="nav-collapse")

      b-collapse(is-nav)#nav-collapse
        b-navbar-nav(right).ml-auto
          b-nav-item(to="/" exact exact-active-class="active") Главная
          b-nav-item(to="/locations" no-prefetch exact exact-active-class="active") Локации
          //b-nav-item(to="/signup") Зарегистрироваться
          b-nav-item(v-if="!loggedIn" to="/login" exact exact-active-class="active") Войти
          b-nav-item(v-if="loggedIn" @click="logout")
            em Привет {{ user.name }}
          b-nav-item(v-if="loggedIn" @click="logout") Выйти
</template>

<script>
import { mapState } from 'vuex'
export default {
  name: 'NavBar',
  computed: {
    ...mapState('auth', ['loggedIn', 'user'])
  },
  methods: {
    async logout() {
      await this.$auth.logout()
      this.$router.push('/login')
    }
  }
}
</script>

<style lang="scss">
.mb50{
  margin-bottom: 50px;
}
.nav-item{
  font-family: 'Open Sans Condensed', sans-serif;
  font-weight: bold;
  font-size: 1.2rem;
  letter-spacing: 1px;
}
.navbar-brand{
  font-family: 'Open Sans Condensed', sans-serif;
  font-size: 1.3rem;
  font-weight: bold;
  text-transform: uppercase;
}
.highlighted{
  display: inline-block;
  margin-left: 10px;
  padding: 0 10px;
  font-weight: bold;
  letter-spacing: 1px;
  font-size: 1.3rem;
  text-transform: lowercase;
  background: #FF3366;
  color: #fff;
}
.navbar-dark .navbar-nav .show > .nav-link, .navbar-dark .navbar-nav .active > .nav-link, .navbar-dark .navbar-nav .nav-link.show, .navbar-dark .navbar-nav .nav-link.active {
    color: #FF3366;
}
</style>