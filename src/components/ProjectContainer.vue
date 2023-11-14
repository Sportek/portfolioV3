<script setup lang="ts">
import { reactive } from 'vue'
import IconArrow from './icons/IconArrow.vue'
import IconGithub from './icons/IconGithub.vue'

const projects: Project[] = [
  {
    title: 'Projet système embarqué - 2023',
    description:
      'Effectué dans le cadre du cours INF1900 et en équipe de 6, le projet avait pour but de développer différents système pour permettre à un robot d’effectuer un parcours tout en sauvegardant en mémoire différents points stratégiques pour ensuite cartographier les différents obstacles présents.',
    learning_achieved: [
      'Travailler en équipe avec GitHub',
      'Recherche dans différentes documentations',
      'Mise en pratique de mes connaissances en C++',
      'Utilisation d’une carte à microcontrôleur',
      'Automatisation de certaines tâches avec des scripts Makefiles et Shell'
    ],
    technologies: ['C++', 'Makefiles', 'Shell'],
    github_link: 'https://github.com/polytechnique-school-work/INF1900-Final',
    project_image: 'https://i.imgur.com/fMc8L8K.jpg'
  },
  {
    title: 'Portfolio - 2023',
    description: 'TODO',
    learning_achieved: ['Design complet avec Figma', 'Développement en différents composants'],
    technologies: ['TypeScript', 'VueJS', 'HTML/CSS', 'Figma'],
    github_link: 'https://github.com/Sportek/portfolioV3',
    project_image: 'https://i.imgur.com/uYoHqRF.png'
  },
  {
    title: 'Commissions bot Discord - 2020/2022',
    description:
      'Mise en vente de différentes applications Discord à différents clients. Vente sous forme de plusieurs modules déjà réalisés ou développement de modules personnalisés pour les clients. Ces applications avaient généralement pour but de réaliser des actions d’automatisation pour aider à la gestion de la communauté de mes clients.',
    learning_achieved: [
      'Écouter et réaliser les demandes des clients',
      'Maintenir une  base de code dans le temps',
      'Modularisation des différents systèmes',
      'Mise en place sur différents systèmes Linux'
    ],
    technologies: ['TypeScript', 'NodeJS', 'DiscordJS', 'PM2 ou Pterodactyl'],
    github_link: 'https://github.com/Sportek/DiscordApplication',
    project_image: 'https://i.imgur.com/QNRWBbE.png'
  },
  {
    title: "Jeu d'échecs - 2023",
    description: 'TODO',
    learning_achieved: [
      'Développement orienté objet',
      'Mise en pratique de mes connaissances en C++',
      'Mise en place de tests permettant une couverture complète du code'
    ],
    technologies: ['C++', 'Qt'],
    github_link: 'https://github.com/polytechnique-school-work/INF1015-Echec',
    project_image: 'https://i.imgur.com/xQnS3qC.png'
  }
]

const state = reactive({
  project: projects[0],
  index: 0
})

const changePage = (side: 'left' | 'right') => {
  const maxIndex = projects.length - 1 // Supposons que 'projects' est votre liste de projets

  if (side === 'right') {
    // Si le côté est 'right', augmentez l'index
    state.index = (state.index + 1) % (maxIndex + 1)
  } else if (side === 'left') {
    // Si le côté est 'left', diminuez l'index
    state.index = (state.index - 1 + projects.length) % projects.length
  }

  state.project = projects[state.index]
}
</script>

<template>
  <div class="project">
    <div class="container">


      <div class="project-container">
        <div class="data-container">
          Salut
        </div>
      </div>


      <div class="arrows">
        <IconArrow class="arrow" rotation="left" @click="changePage('left')" />
        <div class="dots">
          <div v-for="index in projects.length" v-bind:key="index">
            <div v-if="index - 1 === state.index">
              <svg xmlns="http://www.w3.org/2000/svg" width="10" height="10" viewBox="0 0 10 10" fill="none">
                <circle cx="5" cy="5" r="5" fill="#F27B00" />
              </svg>
            </div>
            <div v-else>
              <svg xmlns="http://www.w3.org/2000/svg" width="10" height="10" viewBox="0 0 10 10" fill="none">
                <circle cx="5" cy="5" r="5" fill="#AF6E46" />
              </svg>
            </div>
          </div>
        </div>
        <IconArrow class="arrow" rotation="right" @click="changePage('right')" />
      </div>
    </div>
  </div>
</template>

<style scoped>
.github>a {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: left;
  gap: 0.5em;
  color: var(--color-gold);
  width: fit-content;
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
  justify-content: center;
  align-items: center;
}


.project-container {
  width: 100%;
  height: 100%;
}

.data-container {
  background-color: darkred;
  width: 100%;
  min-height: 100%;
  overflow: auto;
}

/* .text-container {
  height: 100%;
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.image-container {
  width: 40%;
  padding: 2rem;
  display: flex;
  align-items: center;
  justify-content: center;
}

img {
  border: 3px;
  border-radius: 10px;
  border-color: var(--color-gold);
  border-style: solid;
  max-width: 300px;
  max-height: 300px;
} */

/* .description-container {
  display: flex;
  flex-direction: column;
  width: 60%;
  gap: 1rem;
}

.information-container {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
} */

.container {
  display: flex;
  flex-direction: column;
  /* padding: 1rem 3.125rem; */
  border: 3px;
  border-radius: 10px;
  border-color: var(--color-gold);
  border-style: solid;
  width: 100%;
  height: 100%;
  overflow: auto;
  position: relative;
}

/* .data-container {
  display: flex;
  flex-direction: row;
  height: 100%;
}

img {
  height: 100%;
  width: 100%;
  object-fit: cover;
} */

.arrows {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  /* background-color: var(--color-secondary); */
  align-items: center;
  width: 100%;
  color: var(--color-gold);
  padding: 0 2rem;
}

.arrows>.arrow {
  display: flex;
  align-items: center;
  justify-content: center;
}


/* #title {
  color: var(--color-text);
  font-family: Poppins;
  font-size: 1.5rem;
  font-style: normal;
  font-weight: 700;
  line-height: normal;
}

.information-title {
  color: var(--color-text);
  font-family: Poppins;
  font-size: 1.125rem;
  font-style: normal;
  font-weight: 500;
  line-height: normal;
}

.information-description {
  color: var(--color-text);
  font-family: Poppins;
  font-size: 0.875rem;
  font-style: normal;
  font-weight: 400;
  line-height: normal;
} */

.dots {
  display: flex;
  flex-direction: row;
  gap: 0.5rem;
  justify-content: center;
  align-items: center;
  height: 100%;
}

.arrow:hover {
  color: var(--color-accent);
  cursor: pointer;
}

@media screen and (max-width: 768px) {
  .description-container {
    width: 100%;
  }

  .image-container {
    display: none;
  }
}
</style>
