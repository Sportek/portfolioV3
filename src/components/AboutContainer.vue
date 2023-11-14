<script setup lang="ts">
    import DiscoverMoreContainer from "@/components/DiscoverMoreContainer.vue"
</script>

<template>
    <div class="about">
        <div class="container">
            <div class="text-container">
                <div class="text">Hello</div>
                <div>
                    <div class="text">I'm </div>
                    <div class="name">Gabriel Landry</div>
                </div>
                <div class="text">
                    Second year student in software engineering at Polytechnique Montréal. Here you will find various information about me. If you want more, do not hesitate to <a href="#contact">contact me</a>! 
                </div>
            </div>
        </div>
        <DiscoverMoreContainer/>
    </div>
</template>

<style scoped>
    .about {
        width: 100%;
        height: 100%;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        gap: 5em;
    }

    .container {
        border-radius: 0.625rem;
        border: 2px solid var(--color-gold);
        background: var(--color-background);
        display: flex;
        padding: 3.125rem;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        gap: 0.625rem;
    }
    .text-container {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        align-self: stretch;
        max-width: 40rem;
    }

    .text {
        color: var(--color-text);
        font-family: Poppins;
        font-size: 1.125rem;
        font-style: normal;
        font-weight: 500;
        line-height: normal;
    }

    .name {
        font-family: Poppins;
        font-size: 2.25rem;
        font-style: normal;
        font-weight: 700;
        line-height: normal;
        background: linear-gradient(270deg, #F27B00 70.9%, #B75709 89.23%, #4D1819 120.95%);
        background-clip: text;
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
    }

    a {
        color: var(--color-gold);
    }
</style>