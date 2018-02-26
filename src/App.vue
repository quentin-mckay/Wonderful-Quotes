<template>
  <div class="container">
    <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
    
    <app-new-quote @quoteAdded="addQuote"></app-new-quote>
    
    <hr>
    <app-quote-grid :quotes="quotes" @quoteDeleted="deleteQuote"></app-quote-grid>

    <hr>
    <section class="info-box">
      <p>Info: Click on a Quote to delete it</p>
    </section>
  </div>  
</template>

<script>
import QuoteGrid from './components/QuoteGrid'
import NewQuote from './components/NewQuote'
import Header from './components/Header'

export default {
  components: {
    appHeader: Header,
    appNewQuote: NewQuote,
    appQuoteGrid: QuoteGrid,
  },
  data() {
    return {
      maxQuotes: 12,
      quotes: ['"Dance like no one is watching"']
    }
  },
  methods: {
    addQuote(quote) {
      if (this.quotes.length >= this.maxQuotes) {
        return alert('Maximum storage reached. Please delete a quote before adding a new one.')
      }  
      this.quotes.push(`"${quote}"`)
    },
    deleteQuote(index) {
      this.quotes.splice(index, 1)
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Poppins|Ruluko');


body {
  background: white;
  font-family: Poppins, sans-serif;
}

.container {
  max-width: 900px;
  margin: 1rem auto;
}



.info-box {
  margin-top: 1rem;
  background: lightblue;
  border-radius: 3px;
  border: 1px solid rgba(0, 0, 255, 0.253);
  padding: 1px 1rem;
}

</style>
