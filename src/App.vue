<template>
    <div class="container">
       <appNewQuote @quoteAdded="NewQuote"></appNewQuote>
       <appQuoteGrid :quotes="Quotes" @quoteDeleted="deleteQuote"></appQuoteGrid> 
       <div class="row">
           <div class="col-sm-12 text-center">
               <div class="alert alert-info">Info: Click on a Quote to delete it!</div>
           </div>
       </div>
    </div>
</template>

<script>
    import QuoteGrid from './components/QuoteGrid.vue';
    import NewQuote from './components/NewQuote.vue';
    export default {
        data: function() {
            return {
                Quotes: [
                    'Simple Quote'
                ],
                maxQuotes: 10
            }
        },
        methods: {
           NewQuote: function(Quote) {
               this.Quotes.push(Quote);
           },
           deleteQuote(index) {
              this.Quotes.splice(index, 1);
           }
        },
        components: {
            appQuoteGrid: QuoteGrid,
            appNewQuote: NewQuote
        }
        
    }
</script>

<style>
</style>
