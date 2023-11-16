<script setup lang="ts">
import { ref } from 'vue'
import IconFlagFR from './icons/IconFlagFR.vue'
import IconFlagUSA from './icons/IconFlagUSA.vue'

const language = ref(navigator.language.startsWith('fr') ? 'fr' : 'en')

const changeLanguage = () => {
  language.value = language.value === 'fr' ? 'en' : 'fr'
}
</script>

<template>
  <div class="header">
    <div id="language-button" @click="changeLanguage()">
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
