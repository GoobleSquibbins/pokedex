<template>
    <div>
        <div>
            <div class="w-[560px] m-[20px] rounded overflow-hidden shadow-2xl hover:bg-[#152856] hover:shadow-[#152856] hover:text-white transition ease-in-out delay-75">
                <div class="video">
                    <iframe width="560" height="315" :src="image"
                        title="YouTube video player" frameborder="0"
                        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
                        allowfullscreen></iframe>
                </div>
                <div class="px-6 py-4 text-center">
                    <div class="font-bold text-xl mb-2">
                        <h1>
                            このトピックはアルビノという名前のユーチューバーから盗みました
                        </h1>
                    </div>
                    <p>彼のコンテンツを見てください</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
const props = defineProps({
 image: String,
 title: String
})
</script>

<style lang="scss" scoped></style>