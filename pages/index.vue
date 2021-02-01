<template>
  <div class="container">
    <signin-vue v-if="!user" @setUser="setUser" />
    <compliments-vue v-else :user="user" />
  </div>
</template>

<script>
import ComplimentsVue from '~/components/Compliments.vue'
import SigninVue from '~/components/Signin.vue'

export default {
  components: {
    ComplimentsVue,
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

<style>
.container {
  padding: 0 0.8rem;
  position: relative;
}
</style>
