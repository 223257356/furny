<script>
  export default {
    props: {
      product: Object
    },
    methods: {
      addToCart() {
        this.$emit('add-to-cart', this.product.id);
      }
    }
  }
</script>

<template>
    <div class="product-item">
      <img :src="product.image" alt="Product Image" />
      <h3>{{ product.name }}</h3>
      <div class="product-description" v-html="product.description"></div>
      <p>${{ product.price }}</p>
      <button @click="addToCart">Add to Cart</button>
    </div>
</template>

<style scoped>
.product-item img {
  width: 250px; /* Set the desired width */
  height: 250px; /* Set the desired height */
  object-fit: cover; /* Optional: Controls how the image fits within the dimensions */
}

.product-description {
    font-style: italic;
}
</style>
