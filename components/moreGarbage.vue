<template>
    <div> 
        <div class="w-[200px] mb-[20px] rounded overflow-hidden shadow-2xl m-[10px] hover:bg-[#152856] hover:text-white hover:shadow-[#152856] transition ease-in-out delay-75">
            <div class="video">
                <img class="h-[200px]" :src="image" alt="">
            </div>
            <div class="px-6 py-4">
                <div class="font-bold text-xl mb-2 text-center">{{ title }}</div>
            </div>
        </div>
    </div>
</template>

<script setup>
const props = defineProps({
    image: String,
    text: String,
    title: String
})
</script>

<style lang="scss" scoped></style>