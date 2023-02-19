<template>
    <div class="row items-start justify-start">
        <div class="px-lg cursor-pointer text-bold text-sm" :class="{'active' : !showComments}" @click="toggleContent()">{{ introTitle }}</div>
        <div class="px-lg cursor-pointer text-bold text-sm" :class="{'active' : showComments}" @click="toggleContent('comments')">{{ commentsTitle }}</div>
        <div class="col-12" v-if="showComments">
            <div v-for="item in comments" :key="item" class="card my-md pa-md text-md">{{ item }}</div>
        </div>
        <div class="col-12 my-md text-md" v-else>{{ intro }}</div>
    </div>
</template>


<script setup>
import { computed, defineProps, ref } from 'vue';

const introTitle = "معرفی محصول"
const commentsTitle = "کامنت ها"

const props = defineProps({
    comments: Array,
    intro: String
})

const intro = computed(() => props.intro)
const comments = computed(() => props.comments)

const showComments = ref(false)

const toggleContent = (content) => {
    content == 'comments' ? showComments.value = true : showComments.value = false
}

</script>

<style scoped>

.active {
    color: #ef394e;
    border-bottom: 2px solid #ef394e;
    padding-bottom: .5rem;
}
</style>