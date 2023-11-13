<script setup lang="ts">
import IconGithub from "./icons/IconGithub.vue"

defineProps<{
    project: Project
}>()
</script>

<template>
    <div class="project">


        <div class="description-container">
                    <div id="title">{{ project.title }}</div>
                    <div class="information-container">
                        <div class="information-title">Description du projet :</div>
                        <div class="information-description">{{ project.description }}</div>
                    </div>
                    <div class="information-container">
                        <div class="information-title">Apprentissage réalisés :</div>
                        <div class="information-description">
                            <ul>
                                <li v-for="item in project.learning_achieved" v-bind:key="item.toString()">{{ item }}</li>
                            </ul>
                        </div>
                    </div>
                    <div class="information-container">
                        <div class="information-title">Technologies utilisées :</div>
                        <div class="information-description">
                            <ul>
                                <li v-for="item in project.technologies" v-bind:key="item.toString()">{{ item }}</li>
                            </ul>
                        </div>
                    </div>
                    <div class="github">
                        <a :href="project.github_link" target="_blank">
                            <IconGithub/>
                            <div id="github-text">
                            GitHub du projet
                        </div>
                    </a>
                </div>
            </div>


        <!-- <div class="container">
            <div class="image-container">
                <img :src="project.project_image" width="150" height="150" alt="image">
            </div>
        </div>
        <div>

        </div> -->
    </div>
</template>

<style scoped>

    .project {
        width: 100%;
        height: 100%;
        box-sizing: border-box;
        background-color: red;
    }


    /* .github > a {
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: left;
        gap: 0.5em;
        color: var(--color-gold);
    }

    #github-text {
        color: var(--color-text);
        font-family: Poppins;
        font-size: 1.125rem;
        font-style: normal;
        font-weight: 500;
        line-height: normal;
    }

    #github-text:hover {
        color: var(--color-orange);
    }

    .project {
        width: 100%;
        height: 100%;
        display: flex;
        flex-direction: column;
        box-sizing: border-box;
        max-width: 100%;
    }

    .description-container {
        display: flex;
        flex-direction: column;
    }

    .container {
        display: flex;
        flex-direction: row;
        padding: 3.125rem 3.125rem 0.625rem 3.125rem;
    } */
</style>