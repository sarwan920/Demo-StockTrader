<template>
  <div>
    <h1>Trade or View your Portfolio</h1>
    <h6>You may save & Load your data</h6>
    <h6>Click on 'End Day' to begin New Day!</h6>
    <p>Your Funds:{{ funds }}</p>
  </div>
</template>

<script>
export default {
  computed: {
    funds() {
      return this.$store.getters.funds;
    },
  },
};
</script>

<style></style>
