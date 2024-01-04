<template>
  <v-app id="home">
    <NavBar class="fixed-navbar"/>
    <v-container fluid>
      <div class="head">
        <v-row>
          <v-col cols="5">
            <div style="position: relative" class="mt-16">
              <h1 class="text-grey">Hi</h1>
              <h1 class="text-white">I'm Sabitri Shrestha</h1>
              <span class="text-grey">Web Developer</span><br/>
              <v-btn tile dark class="text-yellow mt-8" variant="outlined">Contact Me</v-btn>
            </div>
          </v-col>
          <v-col cols="2">
          </v-col>
          <v-col cols="5">
            <div style="position: relative;z-index: 9999;" class="mt-10">
              <v-img src="pp.jpg" conatin max-height="300"></v-img>

            </div>
          </v-col>
        </v-row>

      </div>
      <v-col cols="12" class="mt-10" id="about">
        <h2 class="mt-10 text-white">About Me</h2>
        <p class="text-grey mt-10" style="font-size:20px;">
          I am a positive and passionate person living in Australia. In my professional life, I find problems as an opportunity to learn something new. Over the years, I've built products for businesses and companies ranging from plugins to complex solutions with focus on best user experience.
          The joy of creating keeps me motivated in my work. I am eager to learn new technologies and I value collaboration, quality and innovation in my work. I love spending time with my plants, music and my family.
        </p>
      </v-col>
      <v-col cols="12" class="mt-10" id="skills">
        <h2 class="mt-10 text-white">Skills</h2>
        <div class="mt-10">
          <span class="skill-btn text-grey">HTML</span>
          <span class="skill-btn text-grey">CSS</span>
          <span class="skill-btn text-grey">JavaScript</span>
          <span class="skill-btn text-grey">jQuery</span>
          <span class="skill-btn text-grey">Ajax</span>
          <span class="skill-btn text-grey">TypeScript</span>
          <span class="skill-btn text-grey">Vue</span>
          <span class="skill-btn text-grey">PHP</span>
          <span class="skill-btn text-grey">Laravel</span>
          <span class="skill-btn text-grey">Docker</span>
          <span class="skill-btn text-grey">Git</span>
          <span class="skill-btn text-grey">Jira</span>
          <span class="skill-btn text-grey">Postman</span>
          <span class="skill-btn text-grey">Scrum</span>
        </div>
      </v-col>
      <v-col cols="12" class="mt-06" id="projects">
        <h2 class="mt-10 text-white">Projects</h2>
        <v-row class="mt-10">
          <v-col cols="6" v-for="project in projects" :key="project.id">
            <v-card @click="openLink(project.githubLink)" class="project-cards">
              <v-card-item>
                <div>
                  <div class="text-h5 mb-1 text-white text-center">
                   {{ project.title}}
                  </div>
                  <div class="project-card-languages mt-10" v-if="project.languages && project.languages.length">
                    <span v-for="language in project.languages" :key="language" class="text-grey">{{ language }}</span>
                  </div>

                </div>
              </v-card-item>

            </v-card>
          </v-col>
        </v-row>
      </v-col>
      <v-footer class="d-flex flex-column mt-10" color="#1a1917" id="contact">
        <div class="d-flex w-100 align-center px-4">
          <h2 class="text-white mt-10">Contact Me!</h2>

          <v-spacer></v-spacer>
          <v-btn icon="fas fa-envelope" class="contact-link mr-4" variant="outlined" @click="openLink('mailto:sabitri.shrestha03@gmail.com')">
          </v-btn>
          <v-btn icon="fa-brands fa-linkedin" class="contact-link mr-4" variant="outlined" @click="openLink('https://www.linkedin.com/in/sabitri-shrestha/')">
          </v-btn>
          <v-btn  icon="fa-brands fa-github" class="contact-link mr-4" variant="outlined" @click="openLink('https://github.com/sabitri-shrestha/')">
          </v-btn>
        </div>
      </v-footer>

    </v-container>
  </v-app>

</template>

<script lang="ts">
import { defineComponent } from 'vue';


import NavBar from "@/components/NavBar.vue";


export default defineComponent({
  name: 'HomeView',
  data(){
    return{
      projects: [
        { id: 1, title: 'Laravel Ambassador', githubLink: 'https://github.com/sabitri-shrestha/laravel-ambassador', languages: ['Laravel', 'Vue'] },
        { id: 2, title: 'Vue Admin', text: 'Project 4', githubLink: 'https://github.com/sabitri-shrestha/vue-admin',languages: ['Vue'] },
        { id: 3, title: 'Landon App', githubLink: 'https://github.com/sabitri-shrestha/landon_app' ,languages: ['React']},
        { id: 4, title: 'Simple Social', githubLink: 'https://github.com/sabitri-shrestha/bucketlist' ,languages: ['Python'] },

      ],
    }
  },
  methods: {
    openLink(link: string) {
      // Open GitHub link in a new tab/window
      window.open(link, '_blank');
    }
  },
  components: {
    NavBar,
  },
});
</script>
<style scoped>
  .v-container{
    padding: 90px !important;
    background: #1a1917;
  }
  .head{
    position: relative;
    text-align: center;
    padding:12px;
    margin-bottom: 6px;
    height: 400px;
    width: 100%;
    color: white;

  }
  .head:before{
    content: " ";
    position: absolute;
    top:0;
    left:0;
    height:100%;
    width: 50%;
    background-color: #9e9e9e2b;
    tranform: skew(0deg, 6deg)


  }
  .head:after{
    content: " ";
    position: absolute;
    top:0;
    right:0;
    height:100%;
    width: 50%;
    background-color: #9e9e9e2b;
    tranform: skew(0deg, -6deg)
  }
  .project-cards{
    background-color: #9e9e9e2b;
  }
  .skill-btn {
    display: inline-block;
    padding: 8px 12px;
    margin: 5px;
    background-color: #9e9e9e2b;
    border-radius: 4px;
    cursor: default;
  }
  .project-card-languages{
    align-self: inherit;
    display: flex;
    gap: 15px;
  }
  .contact-link {
    margin-top: 10px;
    margin-bottom: 10px;
  }
  .contact-container{
    background-color: #9e9e9e2b;
  }
  .fixed-navbar {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    z-index: 10000; /* Adjust as needed */
  }
</style>
