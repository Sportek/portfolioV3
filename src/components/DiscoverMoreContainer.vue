<script setup lang="ts">
import IconScrollDownVue from './icons/IconScrollDown.vue';

</script>

<template>
    <div id="container">
        Discover More
        <IconScrollDownVue/>
    </div>
</template>

<style scoped>
    #container {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        color: var(--color-gold);
        gap: 0.5rem;

        font-family: Poppins;
        font-size: 1.125rem;
        font-style: normal;
        font-weight: 700;
        line-height: normal;
    }

    IconScrollDown {
        color: var(--color-gold);
    }
</style>