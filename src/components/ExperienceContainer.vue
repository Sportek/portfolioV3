<script setup lang="ts">
import DiscoverMoreContainer from './DiscoverMoreContainer.vue';
import ProjectContainer from "./ProjectContainer.vue"

const project: Project = {
    title: "Projet système embarqué - 2023",
    description: "Effectué dans le cadre du cours INF1900 et en équipe de 6, le projet avait pour but de développer différents système pour permettre à un robot d’effectuer un parcours tout en sauvegardant en mémoire différents points stratégiques pour ensuite cartographier les différents obstacles présents.",
    learning_achieved: ["Travailler en équipe avec GitHub", "Recherche dans différentes documentations", "Mise en pratique de mes connaissances en C++", "Utilisation d’une carte à microcontrôleur", "Automatisation de certaines tâches avec des scripts Makefiles et Shell"],
    technologies: ["C++", "Makefiles", "Shell"],
    github_link: "https://github.com/polytechnique-school-work/INF1900-Final",
    project_image: "https://i.imgur.com/fMc8L8K.jpg"
}

</script>

<template>
    <div class="experience">
        EXPERIENCE
        <ProjectContainer :project="project"/>
        <DiscoverMoreContainer/>
    </div>
</template>

<style scoped>
    .experience {
        display: flex;
        padding: 3.125rem;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        gap: 1.5625rem;
    }
</style>