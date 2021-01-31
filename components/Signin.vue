<template>
  <div>
    <form @submit.prevent="handleSubmit">
      <h2>Please enter your name</h2>
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
