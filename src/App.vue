<template>
    <div class="container">
      <app-new-quote @quoteAdded="createNewQuote"></app-new-quote>
      <app-quote-grid :quotes="quotes"></app-quote-grid>
    </div>
</template>

<script>
import QuotesGrid from "./components/QuotesGrid.vue";
import NewQuote from "./components/NewQuote.vue";

export default {
  data: function() {
    return {
      quotes: ["Just a Quote to see something"],
      maxQuotes: 10
    };
  },
  methods: {
    createNewQuote(quote) {
      this.quotes.push(quote);
    }
  },
  components: {
    appQuoteGrid: QuotesGrid,
    appNewQuote: NewQuote
  }
};
</script>

<style>

</style>
