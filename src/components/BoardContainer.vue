<script setup lang="ts">
import LeftBarComponent from '@/components/LeftBarComponent.vue';
</script>

<template>
    <div class="board">
        <section class="leftbar">
            <LeftBarComponent />
        </section>
        <section class="header"></section>
        <section class="body">
            <slot/>
        </section>

    </div>
</template>

<style scoped>
.board {
    width: 100vw;
    display: grid;
    grid-template-areas:
        "leftbar header"
        "leftbar body";
    grid-template-columns: auto 5fr;
    grid-template-rows: auto 4fr;
    gap: 10px;
}

.board > * {
    border: 3px;
    border-radius: 10px;
    border-color: var(--color-gold);
    border-style: solid;
}

section.leftbar {
    grid-area: leftbar;
    /* background-color: red; */
    padding: 4em 2em;
    height: 100vh;
}

section.header {
    grid-area: header;
    /* background-color: orange; */
    height: 50px;
}

section.body {
    grid-area: body;
    width: 100%;
    height: 100%;
    display: block;
    margin: 0 auto;
    overflow-y: scroll;
    scroll-behavior: smooth;
}

slot {
    box-sizing: border-box;
    max-width: 100%;
}

</style>