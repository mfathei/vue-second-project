<template>
    <div class="row">
        
        <form>
            <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
                <label for="#quote">Quote</label>
                <textarea name="quote" id="quote" v-model="quote" rows="3" class="form-control"></textarea>
            </div>
            <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
                <button class="btn btn-primary" @click.prevent="createNew">Add Quote</button>
            </div>
        </form>
    </div>
</template>

<script>
import Quote from "./Quote.vue";

export default {
  data: function() {
    return { quote: "" };
  },
  props: ["quotes"],
  components: {
    appQuote: Quote
  },
  methods: {
    createNew() {
        this.$emit('quoteAdded', this.quote);
        this.quote = '';
    }
  }
};
</script>

<style scoped>

</style>
