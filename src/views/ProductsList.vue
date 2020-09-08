<template lang="pug">
  div.products-list
    div(v-for="(product, index) in $store.getters.products", :key="index", @click="$router.push(`/product/${product.slug}`)")
      img(:src="product.imageUrl")
      h2 {{product.name}}
      p.description {{product.description}}
      p.price ${{product.price}}
      button(@click.stop="deleteProduct(index)") ⓧ
</template>

<script>
export default {
  name: "Products",
  methods: {
    deleteProduct(index) {
      this.$store.commit("deleteProduct", index);
    }
  }
};
</script>

<style scoped>
.products-list {
  display: flex;
  padding-top: 30px;
}
.products-list div {
  width: 33%;

  box-sizing: border-box;
  padding: 30px;
  background-color: lightsalmon;
}

button {
  padding: 30px;
  font-size: 2rem;
  background: transparent;
  border: none;
}

.description,
.price {
  padding-top: 20px;
}
</style>