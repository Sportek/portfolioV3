<script setup lang="ts">
import IconFlagFR from './icons/IconFlagFR.vue'
import IconFlagUSA from './icons/IconFlagUSA.vue'

const language = navigator.language.startsWith('fr') ? 'fr' : 'en'
</script>

<template>
  <div class="header">
    <div id="language-button">
      <IconFlagUSA v-if="language === 'fr'" />
      <IconFlagFR v-else />
    </div>
  </div>
</template>

<style scoped>
#language-button > svg {
  height: 32px;
  width: 32px;
}

#language-button {
  display: flex;
  align-items: center;
  justify-content: right;
  padding: 0 1rem;
}
</style>
