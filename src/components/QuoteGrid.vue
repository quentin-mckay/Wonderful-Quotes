<template>
  <section class="quote-grid">
    <app-quote v-for="(quote, index) in quotes" :key="quote" @click.native="deleteQuote(index)">{{ quote }}</app-quote>
  </section>
</template>

<script>
import Quote from './Quote'

export default {
  props: {
    quotes: Array,
  },
  components: {
    appQuote: Quote
  },
  methods: {
    deleteQuote(index) {
      this.$emit('quoteDeleted', index)
      
    }
  }
}
</script>

<style scoped>
  .quote-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-gap: 1rem;
  }
</style>
