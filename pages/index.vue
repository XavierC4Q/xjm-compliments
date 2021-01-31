<template>
  <div class="container">
    <signin-vue v-if="!user" @setUser="setUser" />
  </div>
</template>

<script>
import SigninVue from '~/components/Signin.vue'

export default {
  components: {
    SigninVue,
  },
  data: () => ({
    user: '',
  }),
  methods: {
    setUser(user) {
      this.user = user
    },
  },
}
</script>

<style></style>
