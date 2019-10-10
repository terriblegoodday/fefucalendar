<template>
  <header>
    <b-navbar fixed=top type="light" class='navbar'>
      <div class="container">
        <b-navbar-brand>CalSync</b-navbar-brand>
        <b-navbar-nav v-if="this.$auth.loggedIn">
          <b-nav-item>Расписание</b-nav-item>
          <b-nav-item>Синхронизация</b-nav-item>
        </b-navbar-nav>
        <b-navbar-nav class='ml-auto'>
          <b-nav-item><custom-icon name='github' class='gh-icon'/> Github</b-nav-item>
        </b-navbar-nav>
      </div>
    </b-navbar>
  </header>
</template>

<style lang="sass" scoped>
.navbar
  .container
    max-width: 1024px
    margin: 0 auto

.gh-icon
  width: 18px
</style>

<script>
import customIcon from 'vue-icon/lib/vue-feather.esm'

export default {
  components: {
    customIcon
  }
}
</script>
