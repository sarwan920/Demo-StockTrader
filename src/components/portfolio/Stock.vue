<template>
  <div class="card m-3 bg-light" style="width: 15rem;">
    <div class="card-header bg-info text-white border-dark">
      <h5 class="card-title">
        {{ stock.name }}
        <small>(Price:{{ stock.price }} Quantity:{{ stock.quantity }})</small>
      </h5>
    </div>
    <div class="card-body">
      <input type="number" class="form-control" v-model="quantity" />
      <button
        @click="sellStock"
        :disabled="quantity <= 0"
        class="btn btn-info mt-2"
      >
        Sell
      </button>
    </div>
  </div>
</template>

<script>
import { mapActions } from "vuex";
export default {
  props: ["stock"],
  data() {
    return {
      quantity: 0,
    };
  },
  methods: {
    ...mapActions({
      placeSellOrder: "sellStock",
    }),
    sellStock() {
      const order = {
        stockId: this.stock.id,
        stockPrice: this.stock.price,
        quantity: this.quantity,
      };

      this.placeSellOrder(order);
      this.quantity = 0;
    },
  },
};
</script>

<style></style>
