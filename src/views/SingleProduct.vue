<template lang="pug">
  .container
    .content
      h1 {{product.name}}
      p.description {{product.description}}
      p.price ${{product.price}}
    img(:src="product.imageUrl").image
</template>

<script>
export default {
  name: "Product",
  data() {
    return {
      product: {}
    };
  },
  mounted() {
    this.product = this.$store.getters.products
      .filter(item => item.slug === this.$route.params.slug)
      .shift();
  }
};
</script>

<style scoped>
.container {
  display: grid;
  grid-template-columns: 50% 50%;
  padding-top: 50px;
  margin: 0 auto;
  max-width: 1200px;
}
.image {
}

.content h1 {
  padding-bottom: 50px;
}

.description,
.price {
  padding-top: 20px;
}
</style>