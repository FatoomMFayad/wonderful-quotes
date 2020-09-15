<template>
    <div class="container">
       <appQuoteGrid :quotes="Quotes"></appQuoteGrid> 
    </div>
</template>

<script>
    import QuoteGrid from './components/QuoteGrid';
    export default {
        data: function() {
            return {
                Quotes: [
                    'Simple Quote'
                ],
                maxQuotes: 10
            }
        },
        components: {
            appQuoteGrid: QuoteGrid
        }
        
    }
</script>

<style>
</style>
