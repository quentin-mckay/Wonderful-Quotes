<template>
  <section class="new-quote">
    <form>
      <div class="textarea">
        <label>Quote</label>
        <textarea rows="3" cols="60" v-model="quote"></textarea>
      </div>
      
      <button @click.prevent="createNewQuote">Add Quote</button>
    </form>
  </section>
</template>

<script>
export default {
  data() {
    return {
      quote: ''
    }
  },
  methods: {
    createNewQuote() {
      this.$emit('quoteAdded', this.quote)
      this.quote = ''
    }
  }
}
</script>

<style scoped>
.new-quote {
  margin-top: 1rem;
}


form {
  display: flex;
  flex-direction: column;
  align-items: center;
}

label {
  display: block;
}

textarea {
  display: block;
  resize: none;
  border: none;
  overflow: hidden;
  outline: none;
  border: 1px solid grey;
  border-radius: 3px;
  font: inherit;
}

button {
  padding: 0.5rem 1rem;
  margin: 1rem;
  font: inherit;
  background: lightblue;
  border: 1px solid blue;
  border-radius: 3px;
}

</style>
