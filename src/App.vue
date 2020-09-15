<template>
    <div class="container">
        <appHeader :quoteCount="Quotes.length" :maxQuotes="maxQuotes"></appHeader>
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
    import Header from './components/Header.vue'
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
               if(this.Quotes.length >= this.maxQuotes) {
                   return alert('Please delete Quotes First')
               }
               this.Quotes.push(Quote);
           },
           deleteQuote(index) {
              this.Quotes.splice(index, 1);
           }
        },
        components: {
            appQuoteGrid: QuoteGrid,
            appNewQuote: NewQuote,
            appHeader: Header
        }
        
    }
</script>

<style>
</style>
