<template>
    <div class="row items-start justify-start">
        <div class="mx-md cursor-pointer text-bold text-md" @click="toggleContent('intro')">{{ intro }}</div>
        <div class="mx-md cursor-pointer text-bold text-md" @click="toggleContent('comments')">{{ comments }}</div>
    </div>
    <div class="row items-start justify-start my-md">
        <div class="col-12" v-if="commentIsVisible">
            <div v-for="item in commentsContent" :key="item" class="card my-md pa-md text-md">{{ item }}</div>
        </div>
        <div class="col-12 my-md text-md" v-else>{{ introContent }}</div>
    </div>
</template>


<script setup>
import { computed, defineProps, ref } from 'vue';

const intro = "معرفی محصول"
const comments = "کامنت ها"

const props = defineProps({
    comments: Array,
    intro: String
})

const introContent = computed(() => props.intro)
const commentsContent = computed(() => props.comments)

const introIsVisible = ref(true)
const commentIsVisible = ref(false)

const toggleContent = (content) => {
    if(content === "intro") {
        commentIsVisible.value = false
        introIsVisible.value = true
    } else {
        introIsVisible.value = false
        commentIsVisible.value = true
    }
}


</script>