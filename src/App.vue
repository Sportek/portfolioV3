<script setup lang="ts">
import BoardContainer from '@/components/BoardContainer.vue'
import AboutContainer from './components/AboutContainer.vue'
import ExperienceContainer from './components/ExperienceContainer.vue'
import ContactContainer from './components/ContactContainer.vue'
</script>

<template>
  <main>
    <BoardContainer>
      <AboutContainer id="about" class="elements"></AboutContainer>
      <ExperienceContainer id="experience" class="elements"></ExperienceContainer>
      <ContactContainer id="contact" class="elements"></ContactContainer>
    </BoardContainer>
  </main>
</template>

<style>
.elements {
  height: 100%;
}

main {
  overflow-x: hidden;
}
</style>
