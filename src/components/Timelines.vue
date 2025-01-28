<script setup>
import { defineComponent, reactive } from 'vue';

defineComponent({
    name: 'Timelines',
});

const timelines = reactive([
    {
        id: 0,
        icon: 'mdi-book-education',
        color: 'cyan lighten-1',
        title: 'DesafioLATAM',
        position: 'Data Scientist',
        period: 'AUG 2024 — PRESENT',
        description: 'Data Scientist',
    },
    {
        id: 1,
        icon: 'mdi-book-education',
        color: 'cyan lighten-1',
        title: 'Talento Digital',
        position: 'Front-End Developer Trainee',
        period: 'AUG 2024 — JAN 2025',
        description: 'Front-End Developer',
    },
    {
        id: 2,
        icon: 'mdi-briefcase-variant',
        color: 'amber darken-1',
        title: 'Universidad Andrés Bello',
        position: 'Automation and Robotics Engineer',
        period: 'MAR 2019 — JAN 2024',
        description: 'Bachelor of Automation and Robotics Engineer',
    },
]);
</script>

<template>
    <div class="timeline mt-5">
        <h5 class="text-h5 text-uppercase text-center text-deep-orange-accent-2">Education & work</h5>
        <v-timeline class="mt-5">
            <v-timeline-item
                v-for="timeline in timelines"
                :key="timeline.id"
                :dot-color="timeline.color"
                :icon="timeline.icon"
                size="large"
            >
                <template v-slot:opposite>
                    <div
                        :class="`pt-1 headline font-weight-bold text-button text-${timeline.color}`"
                        v-text="timeline.period"
                    ></div>
                </template>
                <div>
                    <h2 :class="`mt-n1 headline font-weight-light mb-4 text-${timeline.color}`">
                        {{ timeline.title }}
                    </h2>
                    <h5 :class="`text-button text-${timeline.color}`">{{ timeline.position }}</h5>
                    <span class="text-subtitle-2">{{ timeline.description }}</span>
                </div>
            </v-timeline-item>
        </v-timeline>
    </div>
</template>
