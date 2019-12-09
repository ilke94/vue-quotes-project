<template>
    <div class="container">
        <app-new-quote @quoteAdded="newQuote"></app-new-quote>
        <app-quote-grid :quotes="quotes"></app-quote-grid>
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">
                    Info: Click on quote to delete it!
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import QuoteGrid from './components/QuoteGrid.vue';
import NewQuote from './components/NewQuote.vue';
    export default {
        components:{
            appQuoteGrid: QuoteGrid,
            appNewQuote: NewQuote
        },
        data() {
            return {
                quotes: [
                    'Test quote'
                ],
                maxQuotes: 10
            }
        },
        methods: {
            newQuote(quote){
                this.quotes.push(quote);
            }
        },
    }
</script>

<style>
</style>
