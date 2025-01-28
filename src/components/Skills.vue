<script setup>
import { computed, defineComponent, reactive, ref } from 'vue';
import { useDisplay } from 'vuetify';

const { xs, sm, md, lg, xlAndUp } = useDisplay();

defineComponent({
    name: 'Skills',
});

const skills = reactive({
    options: [
        {
            id: 1,
            name: 'Back-end',
        },
        {
            id: 2,
            name: 'Front-end',
        },
        {
            id: 3,
            name: 'UI',
        },
        {
            id: 4,
            name: 'DBMS',
        },
        {
            id: 5,
            name: 'DevOps',
        },
        {
            id: 6,
            name: 'Other',
        },
    ],
    items: [
        {
            id: 1,
            option: 2,
            name: 'Vue.js',
            experience: '1 month',
        },
        {
            id: 2,
            option: 3,
            name: 'Vuetify',
            experience: '1 month',
        },
        {
            id: 3,
            option: 3,
            name: 'Bootstrap',
            experience: '3 months',
        },
        {
            id: 4,
            option: 4,
            name: 'MySQL',
            experience: '1 year',
        },
        {
            id: 5,
            option: 4,
            name: 'MongoDB',
            experience: '3 months',
        },
        {
            id: 6,
            option: 4,
            name: 'PostgreSQL',
            experience: '6 months',
        },
        {
            id: 7,
            option: 4,
            name: 'SQL Server',
            experience: '1 month',
        },
        {
            id: 8,
            option: 4,
            name: 'Firebase',
            experience: '1 month',
        },
        {
            id: 9,
            option: 5,
            name: 'AWS',
            experience: '1 month'
        },
        {
            id: 10,
            option: 6,
            name: 'Photoshop',
            experience: '3 months',
        },
        {
            id: 11,
            option: 6,
            name: 'Vite',
            experience: '1 month',
        },
        {
            id: 12,
            option: 1,
            name: 'Python',
            experience: '6 months',
        },
        {
            id: 13,
            option: 6,
            name: 'Arduino',
            experience: '6 months',
        },
        {
            id: 14,
            option: 6,
            name: 'Node-Red',
            experience: '6 months',
        },
        {
            id: 15,
            option: 2,
            name: 'HTML',
            experience: '6 months',
        },
        {
            id: 16,
            option: 2,
            name: 'CSS',
            experience: '6 months',
        },
        {
            id: 17,
            option: 2,
            name: 'JavaScript',
            experience: '6 months',
        },
        {
            id: 18,
            option: 2,
            name: 'SASS',
            experience: '3 months',
        },
        {
            id: 19,
            option: 2,
            name: 'JQuery',
            experience: '3 months',
        },
        {
            id: 20,
            option: 6,
            name: 'Excel',
            experience: '6 months',
        },
        {
            id: 21,
            option: 2,
            name: 'Node.js',
            experience: '6 months',
        },
        {
            id: 22,
            option: 2,
            name: 'Vuex',
            experience: '6 months',
        },
        {
            id: 23,
            option: 6,
            name: 'GitHub',
            experience: '3 months',
        },
    ],
});

const activeOption = ref(null);

const skillItems = computed(() =>
    activeOption.value != null ? skills.items.filter((item) => item.option === activeOption.value) : skills.items,
);

const toggleOption = (option) => (activeOption.value = activeOption.value === option.id ? null : option.id);
</script>
<template>
    <div class="technical-skills">
        <h5 class="text-h5 text-uppercase text-center text-deep-orange-accent-2">Technical skills</h5>
        <v-slide-group show-arrows center-active class="mt-3">
            <v-slide-group-item v-for="option in skills.options" :key="option.id" v-slot="{ isSelected, toggle }">
                <v-btn
                    class="ma-2"
                    rounded
                    :color="option.id === activeOption ? 'deep-orange-accent-1' : undefined"
                    @click="toggleOption(option)"
                >
                    {{ option.name }}
                </v-btn>
            </v-slide-group-item>
        </v-slide-group>
        <v-item-group selected-class="bg-deep-orange-accent-1" class="technical-skills__row">
            <v-row>
                <v-col
                    v-for="skill in skillItems"
                    :key="skill.id"
                    :cols="xs ? 12 : sm ? 6 : md || lg ? 4 : xlAndUp ? 3 : undefined"
                >
                    <v-item v-slot="{ isSelected, selectedClass, toggle }">
                        <v-card :class="['technical-skills__item', selectedClass]" @click="toggle">
                            <div class="text-h5 text-center">{{ isSelected ? skill.experience : skill.name }}</div>
                        </v-card>
                    </v-item>
                </v-col>
            </v-row>
        </v-item-group>
    </div>
</template>

<style scoped>
.technical-skills__row {
    display: flex;
    margin-top: 24px;
}

.technical-skills__item {
    display: flex;
    flex: 0 1 25%;
    align-items: center;
    justify-content: center;
    text-align: center;
    height: 80px;
    user-select: none;
}
</style>
