<script setup>
import { defineComponent, reactive } from 'vue';

defineComponent({
    name: 'ContactInfo',
});

defineProps({
    header: String,
});

const data = reactive([
    {
        icon: 'mdi-cellphone-sound',
        title: 'Phone',
        value: '+ 56 (9) 81 537 900',
        href: 'tel:+56981537900',
        target: null,
    },
    {
        icon: 'mdi-message-text',
        title: 'Telegram',
        value: '@dark4rrow',
        href: 'https://t.me/dark4rrow',
        target: '_blank',
    },
    {
        icon: 'mdi-gmail',
        title: 'Gmail',
        value: 'bastian.mm96@gmail.com',
        href: 'mailto:bastian.mm96@gmail.com',
        target: null,
    },
    {
        icon: 'mdi-github',
        title: 'GitHub',
        value: 'fbastianmaldo',
        href: 'https://github.com/bastianmaldo',
        target: '_blank',
    },
    {
        icon: 'mdi-linkedin',
        title: 'LinkedIn',
        value: 'bastian.maldonado.maulén',
        href: 'https://www.linkedin.com/in/bastián-maldonado-maulén-9739b92b1/',
        target: '_blank',
    },
]);
</script>

<template>
    <div class="contact-info">
        <h5 class="text-h5 text-uppercase text-deep-orange-accent-2">{{ header }}</h5>
        <div class="contact-info__item mt-3" v-for="(item, i) in data" :key="i">
            <div class="contact-info__icon">
                <v-icon size="x-large">{{ item.icon }}</v-icon>
            </div>
            <div class="contact-info__content">
                <span class="text-uppercase text-button">{{ item.title }}</span>
                <a :href="item.href" :target="item.target">{{ item.value }}</a>
            </div>
        </div>
    </div>
</template>

<style scoped>
.contact-info__item {
    display: flex;
    align-items: flex-end;
}

.contact-info__content {
    display: flex;
    flex-direction: column;
    margin-left: 10px;
}
</style>
