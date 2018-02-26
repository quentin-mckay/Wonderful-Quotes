<template>
  <header>
    <h3>Quotes Added</h3>
    <div class="progress-wrapper">
      <div class="progress" :style="progressBarStyle">
        {{ quoteCount }} / {{ maxQuotes }}
      </div>
    </div>
  </header>
</template>

<script>
export default {
  props: ['quoteCount', 'maxQuotes'],
  computed: {
    progressBarStyle() {
      return {
        width: (this.quoteCount / this.maxQuotes * 100) + '%' 
      }
    }
  }
}
</script>

<style scoped>
h3 {
  margin: 0;
}

.progress-wrapper {
  background: lightgrey;
  border-radius: 3px;
}

.progress {
  background: steelblue;
  /* padding needs strange extra bit on the bottom to vertically center the text. not sure why */
  padding: 0.2rem 0 0.4rem;
  height: 20px;
  border-radius: 3px;
  text-align: center;
  color: white;

  transition: 0.3s;
}
</style>
