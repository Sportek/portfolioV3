<script setup lang="ts">
import DiscoverMoreContainer from './DiscoverMoreContainer.vue'
import ProjectContainer from './ProjectContainer.vue'
</script>

<template>
  <div class="experience">
    <div class="title">EXPERIENCE</div>
    <ProjectContainer />
    <DiscoverMoreContainer />
  </div>
</template>

<style scoped>
.experience {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
  height: 100%;
  width: 100%;
  box-sizing: border-box;
  overflow: hidden;
  /* margin: 0 2rem; */
  /* padding: 3rem; */
}

.title {
  /* Test */
  color: var(--color-gold);
  font-family: Poppins;
  font-size: 2.25rem;
  font-style: normal;
  font-weight: 700;
  line-height: normal;
  letter-spacing: 0.675rem;
}

@media screen and (max-width: 768px) {
  .experience {
    display: flex;
    flex-direction: column;
    gap: 2rem;
  }
}
</style>
