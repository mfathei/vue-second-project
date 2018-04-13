<template>
    <div class="container">
      <app-header :quotesCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
      <br>
      <app-new-quote @quoteAdded="createNewQuote"></app-new-quote>
      <app-quote-grid :quotes="quotes" @quoteDeleted="deleteQuote"></app-quote-grid>
      <div class="row">
        <div class="col-xs-12 text-center">
          <div class="alert alert-info">Info: click on Quote to delete it!</div>
        </div>
      </div>
    </div>
</template>

<script>
import QuotesGrid from "./components/QuotesGrid.vue";
import NewQuote from "./components/NewQuote.vue";
import Header from "./components/Header.vue";

export default {
  data: function() {
    return {
      quotes: ["Just a Quote to see something"],
      maxQuotes: 10
    };
  },
  methods: {
    createNewQuote(quote) {
      if(this.quotes.length >= this.maxQuotes){
        return alert('Please delete quotes first');
      }
      this.quotes.push(quote);
    },
    deleteQuote(index) {
      this.quotes.splice(index, 1);
    }
  },
  components: {
    appQuoteGrid: QuotesGrid,
    appNewQuote: NewQuote,
    appHeader: Header
  }
};
</script>

<style>

</style>
