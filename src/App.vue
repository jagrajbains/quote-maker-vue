<template>
    <div class="container">
        <Header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></Header>
        <NewQuote @quoteAdded="addNewQuote"></NewQuote>
        <QuoteGrid :quotes="quotes" @deleteQuote='deleteQuote'></QuoteGrid>
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">Info: Click on a quote to delete it.</div>
            </div>
        </div>
    </div>
</template>

<script>
import QuoteGrid from './components/QuoteGrid.vue';
import NewQuote from './components/NewQuote.vue';
import Header from './components/Header.vue';

    export default {
        components: {
            QuoteGrid,
            NewQuote,
            Header
        },
        data: function() {
            return {
                quotes: ['Just a simple quote to see something', 'Just something here'],
                maxQuotes: 10
            }
        },
        methods: {
            addNewQuote(quote) {
                if(this.quotes.length >= this.maxQuotes){
                    return alert('Please delete a few quotes before adding a new one!')
                }
                this.quotes.push(quote)
            },
            deleteQuote(index) {
                this.quotes.splice(index, 1);
            }
        }
    }
</script>

<style>
</style>
