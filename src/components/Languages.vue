<script setup>
import { defineComponent, reactive } from 'vue';

defineComponent({
    name: 'Languages',
});

defineProps({
    header: String,
});

const languages = reactive([
    {
        name: 'Spanish',
        value: 100,
    },
    {
        name: 'English',
        value: 85,
    },
    {
        name: 'Japanese',
        value: 35,
    },
]);
</script>
<template>
    <div class="languages">
        <h5 class="text-h5 text-uppercase text-deep-orange-accent-2">{{ header }}</h5>
        <div v-for="(language, i) in languages" :key="i" class="mt-3">
            <span class="text-subtitle-1 font-weight-light">{{ language.name }}</span>
            <div class="d-flex align-center">
                <v-progress-linear color="deep-orange-accent-1" :model-value="language.value"></v-progress-linear>
                <span class="text-subtitle-1 font-weight-light ml-2">{{ language.value }}%</span>
            </div>
        </div>
    </div>
</template>
