<template lang="pug">
  form(@submit.prevent="addProduct")
    h1 Add Product
    div
      label Name: 
        input(required v-model="name")
    div
      label Price in $: 
        input(required v-model="price")
    div
      label Description: 
        textarea(required v-model="description")
    div
      label Image URL: 
        input(required v-model="imageUrl")
    input(type="submit" value="Add").button
</template>

<script>
export default {
  name: "AddProduct",
  data() {
    return {
      name: "",
      price: 0,
      description: "",
      imageUrl: ""
    };
  },
  methods: {
    addProduct() {
      this.$store.commit("addProduct", {
        name: this.name,
        price: this.price,
        description: this.description,
        imageUrl: this.imageUrl
      });
    }
  }
};
</script>

<style scoped>
input,
textarea {
  border: 1px solid #ccc;
  padding: 20px;
  vertical-align: middle;
}

label {
  vertical-align: middle;
  padding-right: 10px;
}

div {
  display: block;
  padding: 50px;
  font-size: 1.5rem;
}

.button {
  background-color: #2c3e50;
  color: white;
  font-size: 1.5rem;
  width: 50%;
}
</style>