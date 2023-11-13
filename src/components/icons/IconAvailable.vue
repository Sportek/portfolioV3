<script setup lang="ts">
import { COLORS } from '@/colors';

defineProps<{
    selectColor: COLORS,
}>()
</script>
<template>
    <svg xmlns="http://www.w3.org/2000/svg" width="13" height="12" viewBox="0 0 13 12" fill="none">
        <circle cx="6.5" cy="6" r="6" :fill="selectColor"></circle>
    </svg>
</template>
