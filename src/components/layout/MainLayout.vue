<template>
    <div class="row justify-center items-around">
        <RouterLink to="/" class="col-12 text-center"><h1>{{ logoName }}</h1></RouterLink>
    </div>
    <div class="py-md">
        <slot />
    </div>
    <FooterCard />
</template>


<script setup>
import FooterCard from "../cards/FooterCard.vue"
const logoName = "دیجی کالا"
</script>