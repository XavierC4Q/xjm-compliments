<template>
  <div>
    <p class="loading" v-if="loading">Loading...</p>
    <div class="compliments-page" v-else-if="!loading">
      <p class="compliment">{{ compliment }}</p>
      <button type="button" class="primary-btn" @click="getCompliment">
        {{ `Need another compliment ${user}?` }}
      </button>
    </div>
    <p class="error" v-if="error">Failed to get you a compliment 😢</p>
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

<style>
@media screen and (max-width: 767px) {
  .compliments-page {
    margin: 3rem 0 !important;
  }
}

.loading {
  margin-top: 5rem;
}

.compliments-page {
  display: flex;
  justify-content: center;
  margin: 3rem 6rem;
  align-items: center;
  flex-direction: column;
}

.compliment, .loading, .error {
  color: #ef476f;
  font-size: 3.6rem;
  text-align: center;
  margin-bottom: 1.6rem;
}
</style>