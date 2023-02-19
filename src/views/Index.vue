

<template>
  <main>
    <div class="row justify-start items-start">
        <ProductCard v-for="product in ProductData" :key="product.id" class="col-4" :product="product" @click="routeToSingle(product.id)" />
    </div>
  </main>
</template>


<script setup>
import ProductCard from '../components/cards/ProductCard.vue';
import ProductData from "../assets/product_data.json"
import { useRouter } from 'vue-router';

const router = useRouter()

const routeToSingle = (id) => {
  router.push({name: "single product", params: {id}})
  console.log(id)
}

</script>