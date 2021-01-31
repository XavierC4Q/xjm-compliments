<template>
  <div>
    <form>
      <h2>Please enter your name</h2>
      <input type="text" @change="handleChange" :value="user" />
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
  },
}
</script>