<script setup lang="ts">
import { COLORS } from "../colors";
import IconAvailable from "./icons/IconAvailable.vue";
defineProps<{
    name: string,
    title: string,
    status: boolean,
}>()

</script>

<template>
    <div class="profile">
        <img src="../assets/img/logo.png" alt="logo">
        <div class="profile-data">
            <div id="name">{{ name }}</div>
            <div id="title">{{ title }}</div>
            <div class="status">
                <IconAvailable :selectColor="COLORS.GREEN"/>
                <div id="status">{{ status ? "Available for new opportunities" : "Not available" }}</div>
            </div>
        </div>
    </div>
</template>

<style scoped>
    div .profile {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }
    div .profile-data {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }

    div .status {
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        gap: 0.25em;
    }
    #name {
        color: var(--color-text);
        text-align: center;
        font-family: Poppins;
        font-size: 1.5rem;
        font-style: normal;
        font-weight: 700;
        line-height: normal;
    }

    #title {
        color: var(--color-text);
        text-align: center;
        font-family: Poppins;
        font-size: 0.875rem;
        font-style: normal;
        font-weight: 400;
        line-height: normal;
    }

    #status {
        color: var(--color-green);
        text-align: center;
        font-family: Poppins;
        font-size: 0.75rem;
        font-style: normal;
        font-weight: 400;
        line-height: normal;
    }
</style>
