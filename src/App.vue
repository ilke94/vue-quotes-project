<template>
    <div class="container">
        <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
        <app-new-quote @quoteAdded="newQuote"></app-new-quote>
        <app-quote-grid :quotes="quotes" @quoteDeleted="deleteQuote"></app-quote-grid>
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
import Header from './components/Header.vue';
    export default {
        components:{
            appQuoteGrid: QuoteGrid,
            appNewQuote: NewQuote,
            appHeader: Header
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
                if(this.quotes.length >= this.maxQuotes){
                    return alert('Delete quotes first!');
                }
                this.quotes.push(quote);
            },
            deleteQuote(index){                
                this.quotes.splice(index, 1);
            }
        },
    }
</script>

<style>
</style>
