<template>
  <div class="container">
    <div v-if="!this.$auth.loggedIn" class='auth-screen'>
      <Logo />
      <div class="login-prompt">
        <p>Синхронизируйте расписание пар со своим календарем. Нужно всего-лишь войти в аккаунт Google.</p>
        <button class="login-button" @click='google'></button>
      </div>
    </div>
    <div v-else>
    </div>
  </div>
</template>

<script>
import Logo from '../components/Logo.vue'

export default {
  components: {
    Logo
  },
  auth: 'guest',
  methods: {
    async google () {
      await this.$auth.loginWith('google').catch((e) => {
        this.$toast.show('Ошибка при входе', { icon: 'fingerprint' })
      })
    }
  }
}
</script>

<style lang="sass" scoped>
.login-button
  margin-top: 15px
  background: url('~static/btn_google_signin_dark_normal_web.svg') no-repeat left top
  height: 60px
  width: 241.25px
  background-size: cover
  border: none
  &:focus
    background: url('~static/btn_google_signin_dark_focus_web.svg') no-repeat left top
    height: 60px
    width: 241.25px
    background-size: cover
    border: none
  &:active
    background: url('~static/btn_google_signin_dark_pressed_web.svg') no-repeat left top
    height: 60px
    width: 241.25px
    background-size: cover
    border: none

.container
  margin: 0 auto
  min-height: 100vh
  display: flex
  justify-content: center
  align-items: center
  text-align: center

</style>
