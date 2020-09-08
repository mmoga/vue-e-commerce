<template lang="pug">
  table(v-if="$store.getters.cart.length > 0")
    tr
      td(colspan="3")
        h2 Cart
    tr
      th Item
      th Quantity
      th Total Price
    tr(v-for="(item, index) in $store.getters.cart", :key="index")
      td {{item.product.name}}
      td {{item.quantity}}
      td ${{item.quantity * item.product.price}}
</template>

<style scoped>
tr,
th,
td {
  border: 1px solid #333;
  padding: 10px;
}
table {
  margin: 0 auto;
}

button {
  padding: 10px 40px;
  background-color: lightgreen;
  border-color: gray;
}
</style>