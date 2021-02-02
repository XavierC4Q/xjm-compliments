<template>
  <div class="signin-page">
    <form @submit.prevent="handleSubmit">
      <h2>Have you been complimented today?</h2>
      <p>
        If not, let this app fill that void and stoke your ego! Enter your name
        below to get started!
      </p>
      <div class="controls-container">
        <input type="text" :value="user" @input="handleInput" />
        <button type="submit" class="primary-btn" :disabled="!user">
          Get Started
        </button>
      </div>
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

<style>
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

form > h2 {
  margin-bottom: 0.8rem;
}

.controls-container {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.controls-container > input {
  margin: 0.8rem 0;
  width: 24rem;
  height: 2rem;
  font-size: 1.6rem;
  text-align: center;
}
</style>
