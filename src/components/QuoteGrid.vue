<template>
  <div class="row">
    <Quote v-for="(quote, index) in quotes" @click.native="deleteQuote(index)" :key="index">{{ quote }}</Quote>
  </div>
  
</template>
<script>
import Quote from './Quote.vue'
export default {
  props: ['quotes'],
  components: {
    Quote
  },
  methods: {
    deleteQuote(index) {
      this.$emit('deleteQuote', index);
    }
  }
}
</script>
<style scoped>

</style>