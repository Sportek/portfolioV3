<script setup lang="ts">
import ProfileComponent from "./ProfileComponent.vue";
import IconLinkedin from "./icons/IconLinkedin.vue"
import IconGithub from "./icons/IconGithub.vue"
import IconCurriculumVitae from "./icons/IconCurriculumVitae.vue"

</script>

<template>
    <div class="leftbar">
        <ProfileComponent class="mobile" name="Gabriel Landry" title="Software engineering student" status/>
        <hr>
        <nav class="navbar-titles">
            <ul class="text">
                <li><a href="#about" class="text">ABOUT</a></li>
                <li><a href="#experience" class="text">EXPERIENCE</a></li>
                <li><a href="#contact" class="text">CONTACT</a></li>
            </ul>
        </nav>
        <hr>
        <nav class="navbar-icons">
            <ul>
                <li><a href="https://www.linkedin.com/in/gablandry/" target="_blank" class="icons"><IconLinkedin/></a></li>
                <li><a href="https://github.com/Sportek" target="_blank" class="icons"><IconGithub/></a></li>
                <li><a href="src/assets/files/gabriel_cv.pdf" download class="icons"><IconCurriculumVitae/></a></li>
            </ul>
        </nav>
    </div>
</template>

<style scoped>

    .leftbar {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-self: center;
        gap: 1em;
    }
    .navbar-icons ul {
        display: flex;
        flex-direction: row;
        justify-content: center;
        padding: 0;
        align-items: center;
        gap: 1em;
    }

    .navbar-titles ul {
        display: flex;
        flex-direction: columns;
        justify-content: center;
        align-items: center;
        gap: 1em;
    }

    ul li a.text {
        color: var(--color-text);
        text-align: center;
        font-family: Poppins;
        font-size: 1.125rem;
        font-style: normal;
        font-weight: 500;
        line-height: normal;
        letter-spacing: 0.3375rem;
    }

    ul li a.text:hover {
        background-color: unset;
        color: var(--color-gold);
    }

    ul li a.icons {
        color: var(--color-gold);
    }

    .navbar-titles ul {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        padding: 0;
    }
    ul li {
        list-style: none;
    }

    hr {
        width: 100%;
        color: var(--color-gold);
    }

    a {
        display: inline-block;
    }
    a.icons:hover {
        background-color: unset;
        color: var(--color-accent);
    }
</style>
