<template>
    <div class="pa-sm">
        <div class="card row flex-center pa-md product-card cursor-pointer">
        <div class="col-12 text-center product-img">
            <img :src="product.image" />
        </div>
        <div class="col-12 text-center text-md">{{ product.name }}</div>
    </div>
    </div>
</template>


<script setup>
import { computed } from 'vue';
import { defineProps } from "vue";

const props = defineProps({
    product: {
        id: Number,
        name: String,
        image: String
    }
})

const product = computed(() => props.product)

</script>


<style scoped>

.product-card {
    min-height: 20rem;
}

.product-img {
    height: 9rem;
}
.product-img img {
    max-width: 8rem;
}
</style>