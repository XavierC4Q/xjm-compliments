<template>
  <div class="signin-page">
    <form @submit.prevent="handleSubmit">
      <h2>Have you been complimented today?</h2>
      <p>
        If not, let this app fill that void and stoke your ego! Enter your name
        below to get started!
      </p>
      <input type="text" :value="user" @input="handleInput" />
      <button type="submit" :disabled="!user">Get Started</button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'Signin',
  data: () => ({
    user: '',
  }),
  methods: {
    handleInput(e) {
      this.user = e.target.value
    },
    handleSubmit() {
      this.$emit('setUser', this.user)
    },
  },
}
</script>

<style lang="css">
@media screen and (max-width: 767px) {
  .signin-page {
    margin: 0;
  }
}

.signin-page {
  margin: 10% auto;
  display: flex;
  justify-content: center;
  text-align: center;
}

.signin-page > h2 {
  margin-bottom: 1.6rem;
}
</style>
