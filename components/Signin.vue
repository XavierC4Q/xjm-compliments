<template>
  <div>
    <form @submit.prevent="handleSubmit">
      <h2>Have you been complimented today?</h2>
      <p>
        If not, let this app fill that void and stoke your ego! Enter your name
        below to get started!
      </p>
      <input type="text" :value="user" @change="handleChange" />
      <button type="submit">Submit</button>
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
    handleChange(e) {
      this.user = e.target.value
    },
    handleSubmit() {
      this.$emit('setUser', this.user)
    },
  },
}
</script>
