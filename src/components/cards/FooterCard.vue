<template>
    <div class="card row flex-center pa-lg footer-card">
        <div class="col-12 text-center text-lg text-bold">{{ footerText }}</div>
        <router-link to="/about" class="col-12 text-black text-center py-lg">{{ aboutUs }}</router-link>
    </div>
</template>

<script setup>
const footerText = "فروشگاه اینترنتی دیجی کالا، بررسی، انتخاب و خرید آنلاین"
const aboutUs = "درباره ما"
</script>


<style scoped>
.footer-card {
    height: 25vh;
}
</style>