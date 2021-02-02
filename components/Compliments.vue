<template>
  <div>
    <p v-if="loading">Loading...</p>
    <div v-else-if="!loading">
      <p>{{ compliment }}</p>
      <button type="button" class="primary-btn" @click="getCompliment">
        {{ `Need another compliment ${user}?` }}
      </button>
    </div>
    <p v-if="error">Failed to get you a compliment 😢</p>
  </div>
</template>

<script>
export default {
  name: 'Compliments',
  props: {
    user: {
      type: String,
      required: true,
    },
  },
  data: () => ({
    compliment: '',
    loading: false,
    error: false,
  }),
  mounted() {
    this.getCompliment()
  },
  methods: {
    async getCompliment() {
      this.loading = true
      this.error = false
      this.compliment = ''

      try {
        const { compliment } = await this.$axios.$get(
          'https://complimentr.com/api'
        )

        this.compliment = `${this.user}: ${compliment
          .charAt(0)
          .toUpperCase()}${compliment.substring(1)}`
        this.loading = false
      } catch {
        this.error = true
        this.loading = false
      }
    },
  },
}
</script>
