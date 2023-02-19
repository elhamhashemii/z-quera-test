<template>
  <div class="text-center text-lg my-lg">{{ product.name }}</div>
  <div class="pdp px-md row items-canter justify-between">
    <div class="col-4 product-img my-lg text-center">
      <img :src="product.image" :alt="product.name">
    </div>
    <div class="col-8 px-md">
      <PdpTabs :intro="product.description" :comments="product.comments" />
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import { useRoute } from 'vue-router';
import ProductData from "../assets/product_data.json"
import PdpTabs from "../components/PdpTabs.vue"

const route = useRoute()

const productId = route.params.id

const product = ref()

ProductData.map((item) => {
  if(productId == item.id) {
    product.value = item
  }
})

</script>

<style scoped>

.pdp {
  margin: 6rem 0;
}
.product-img img {
  max-width: 100%;
  /* width: 16rem; */
}
</style>