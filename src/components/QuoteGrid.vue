<template>
  <div class="row">
    <addQuote
      v-for="(quote, index) in quotes"
      :key="index"
      @click.native="deleteQuote(index)"
      >{{ quote }}</addQuote
    >
  </div>
</template>

<script>
import Quote from "./Quote.vue";
export default {
  props: ["quotes"],
  components: {
    addQuote: Quote
  },
  methods: {
    deleteQuote(index) {
      this.$emit("quoteDeleted", index);
    }
  }
};
</script>

<style lang="scss"></style>
