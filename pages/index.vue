<template>
  <div class="container"></div>
</template>

<script>
export default {
  data: () => ({
    user: '',
  }),
  mounted() {
    const user = localStorage.getItem('compliments_user') || ''
    this.user = user
  },
  updated() {
    const user = localStorage.getItem('compliments_user') || ''
    this.user = user
  },
  destroyed() {
    localStorage.removeItem('compliments_user')
  },
}
</script>

<style>
</style>
