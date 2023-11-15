<script setup lang="ts">
import { reactive } from 'vue'
import IconArrow from './icons/IconArrow.vue'
import IconGithub from './icons/IconGithub.vue'

const projects: Project[] = [
  {
    title: 'Embedded System Project - 2023',
    description:
      'The project was carried out as part of the INF1900 course and in teams of 6, with the goal of constructing diverse systems that would enable a robot to traverse terrain while saving strategic points in memory and mapping the different obstacles present.',
    learning_achieved: [
      'Working as a team with GitHub',
      'Search in different documents',
      'Putting my C++ knowledge into practice',
      'Using a microcontroller board',
      'Automate certain tasks with Makefiles and Shell scripts'
    ],
    technologies: ['C++', 'Makefiles', 'Shell'],
    github_link: 'https://github.com/polytechnique-school-work/INF1900-Final',
    project_image: 'https://i.imgur.com/fMc8L8K.jpg'
  },
  {
    title: 'Portfolio - 2023',
    description:
      'New version of my old portfolio that had very little information, this new version is made with more modern technologies in web development.',
    learning_achieved: [
      'Complete design with Figma',
      'Development into different components with VueJS'
    ],
    technologies: ['TypeScript', 'VueJS', 'HTML/CSS', 'Figma'],
    github_link: 'https://github.com/Sportek/portfolioV3',
    project_image: 'https://i.imgur.com/uYoHqRF.png'
  },
  {
    title: 'Discord commission bot - 2020/2022',
    description:
      'The sale of various Discord applications to different customers. Customers can choose to purchase either pre-made modules or customized modules. The purpose of these applications was to automate actions to manage the community of my customers.',
    learning_achieved: [
      'Listen and fulfill customer requests',
      'Maintain a code base over time',
      'Setup on different Linux systems'
    ],
    technologies: ['TypeScript', 'NodeJS', 'DiscordJS', 'PM2 or Pterodactyl'],
    github_link: 'https://github.com/Sportek/DiscordApplication',
    project_image: 'https://i.imgur.com/QNRWBbE.png'
  },
  {
    title: 'Chess game - 2023',
    description:
      'The project was carried out as part of the INF1900 course, allowed me to put my software development skills into practice by carrying out a more complex project, without forgetting that it allowed me to learn more in the world of automated tests.',
    learning_achieved: [
      'Object-oriented development',
      'Putting my C++ knowledge into practice',
      'Implementation of tests allowing full coverage of the code'
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
          <div class="text-container">
            <div id="title">{{ state.project.title }}</div>
            <div class="information-container">
              <div class="information-title">Description of the project :</div>
              <div class="information-description">{{ state.project.description }}</div>
            </div>
            <div class="information-container">
              <div class="information-title">Knowledge acquired :</div>
              <div class="information-description">
                <ul>
                  <li v-for="item in state.project.learning_achieved" v-bind:key="item.toString()">
                    {{ item }}
                  </li>
                </ul>
              </div>
            </div>
            <div class="information-container">
              <div class="information-title">Technologies used :</div>
              <div class="information-description">
                <ul>
                  <li v-for="item in state.project.technologies" v-bind:key="item.toString()">
                    {{ item }}
                  </li>
                </ul>
              </div>
            </div>
            <div class="github">
              <a :href="state.project.github_link" target="_blank">
                <IconGithub />
                <div id="github-text">Github project link</div>
              </a>
            </div>
          </div>
          <div class="image-container">
            <img :src="state.project.project_image" class="no-mobile" alt="image" />
          </div>
        </div>
      </div>

      <div class="arrows">
        <IconArrow class="arrow" rotation="left" @click="changePage('left')" />
        <div class="dots">
          <div v-for="index in projects.length" v-bind:key="index">
            <div v-if="index - 1 === state.index">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="10"
                height="10"
                viewBox="0 0 10 10"
                fill="none"
              >
                <circle cx="5" cy="5" r="5" fill="#F27B00" />
              </svg>
            </div>
            <div v-else>
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="10"
                height="10"
                viewBox="0 0 10 10"
                fill="none"
              >
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
.github {
  height: auto;
}
.github > a {
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

/* 0 */
.project {
  height: 75%;
  width: 90%;
}
/* 1 */
.container {
  display: flex;
  flex-direction: column;
  border: 3px;
  border-radius: 10px;
  border-color: var(--color-gold);
  border-style: solid;
  height: 100%;
  width: 100%;
  box-sizing: border-box;
}

/* 2: Devrait contenir les éléments*/
.project-container {
  height: 100%;
  box-sizing: border-box;
  border-radius: 10px;
  background-color: var(--color-secondary);
  overflow: auto;
  flex-grow: 1;
}
/* 3: Devrait contenir toutes les informations */
.data-container {
  overflow-y: auto;
  overflow-x: hidden;
  padding: 1rem;
  min-height: 100%;
}

/* Arrows  */
.arrows {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  color: var(--color-gold);
  padding: 0 2rem;
}

.arrows > .arrow {
  display: flex;
  align-items: center;
  justify-content: center;
}

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

.text-container {
  height: 100%;
  width: 60%;
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

img {
  border: 3px;
  border-radius: 10px;
  border-color: var(--color-gold);
  border-style: solid;
  max-width: 300px;
  max-height: 300px;
}

.image-container {
  width: 40%;
  padding: 2rem;
  display: flex;
  align-items: center;
  justify-content: center;
}

.data-container {
  display: flex;
  flex-direction: row;
  height: 100%;
  justify-content: space-between;
}

img {
  height: 100%;
  object-fit: cover;
}

#title {
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
}

@media screen and (max-width: 768px) {
  .text-container {
    width: 100%;
  }

  .image-container {
    display: none;
  }
}

@media screen and (max-width: 768px) {
  .project {
    height: 600px;
  }
}
</style>
