<template>
 <v-app-bar app color="#1a1917" dark fixed flat class="px-12 header">
  <v-spacer></v-spacer>
  <v-btn text @click="scroll('home')" class="text-white">Home</v-btn>
  <v-btn text @click="scroll('about')" class="text-white">About</v-btn>
  <v-btn text @click="scroll('skills')" class="text-white">Skills</v-btn>
  <v-btn text @click="scroll('projects')" class="text-white">Projects</v-btn>
  <v-btn text @click="scroll('contact')" class="text-white">Contact</v-btn>
 </v-app-bar>
</template>

<script>
    export default {
       methods: {
        scroll(refName) {
         const element = document.getElementById(refName);
         element.scrollIntoView({behaviour: "smooth"});
        }
       }
    }
</script>