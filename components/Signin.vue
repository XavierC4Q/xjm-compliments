<template>
  <div class="signin-page">
    <form @submit.prevent="handleSubmit">
      <h2>Have you been complimented today?</h2>
      <div class="controls-container">
        <label for="username"
          >If not, enter your name below and get unlimited compliments to stoke
          your ego!</label
        >
        <input
          type="text"
          id="username"
          placeholder="Your Name Here"
          :value="user"
          @input="handleInput"
        />
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

@media screen and (max-width: 412px) {
  .controls-container > input {
    width: 100% !important;
  }
}

.signin-page {
  margin: 10% auto;
  display: flex;
  justify-content: center;
  text-align: center;
  color: #ef476f;
}

form > h2 {
  margin-bottom: 0.8rem;
  text-transform: uppercase;
  font-size: 2.4rem;
  letter-spacing: 0.15rem;
}

.controls-container {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.controls-container > label {
  font-size: 1.8rem;
}

.controls-container > input {
  margin: 0.8rem 0;
  width: 24rem;
  height: 2rem;
  font-size: 1.6rem;
  text-align: center;
  border: transparent;
}
</style>
