<script setup>
import { ref } from "vue";

const props = defineProps({
    thumbnails: String,
    galleries: Array,
});

const defaultImage = ref(props.thumbnails);

function changeImage(imageUrl) {
    defaultImage.value = imageUrl;
}
</script>

<template>
    <section id="gallery">
        <img :src="defaultImage" alt="not found" class="w-full mt-6 rounded-2xl" />
        <div class="grid grid-cols-4 gap-4 mt-4">
            <template v-for="gallery in props.galleries" :key="gallery.id">
                <div @click="changeImage(gallery.url)" class="overflow-hidden cursor-pointer rounded-2xl"
                    :class="{ 'ring-2 ring-indigo-500': defaultImage == gallery.url }">
                    <img :src="gallery.url" class="w-full" alt="" />
                </div>
            </template>
        </div>
    </section>
</template>
