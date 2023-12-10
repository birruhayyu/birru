<template>
<div id="my-experience">
    <p id="scroll-text" style="font-size: 250px; z-index: 3; color: grey;">EXPERIENCE</p>
  </div>
  <div style="min-height: 100vh; max-height: fit-content; width: 100%">
    <v-row class="d-flex justify-center align-center experience" style="width: fit-content">
      <v-col>
        <v-row class="d-flex justify-center align-center">
        <v-hover v-slot="{ isHovering, props }">
          <v-card v-if="!aboutme" class="thumbnails" v-bind="props" @click="aboutme = true">
            <v-img
              :aspect-ratio="9/16"
              cover
              :src="require('../assets/me.jpg')"
              style="z-index: 2;"
            >
              <v-expand-transition>
                <div
                  v-if="isHovering"
                  class="d-flex transition-fast-in-fast-out black-trans v-card--reveal text-h3 align-center justify-center text-shades-white"
                  style="height: 100%"
                >
                <p style="font-size: 24px">
                  {{experience[0].time}}<br><i>{{experience[0].title}}</i>
                </p>
                </div>
              </v-expand-transition>
            </v-img>
          </v-card>
          <v-card elevation="6" v-if="aboutme" class="thumbnails" v-bind="props" @click="aboutme = false" style="padding: 5px">
            <p style="font-size: 24px">{{experience[0].title}}</p>
            <p style="font-size: 20px"><i>{{experience[0].company}}</i></p>
            <p style="font-size: 20px; padding-bottom: 30px">{{experience[0].place}}</p>
            <v-divider style="padding-bottom: 30px" thickness="2"></v-divider>
            <ol density="compact" v-for="task of experience[0].tasks" :key="task" style="background: transparent; text-align: left; padding-left: 10px">
              <v-list-item density="compact" style="font-size: 18px" prepend-icon="mdi-vector-point">{{task}}</v-list-item>
            </ol>
          </v-card>
        </v-hover>
        </v-row>
      </v-col>
      <v-col>
        <v-row class="d-flex justify-center align-center">
        <v-hover v-slot="{ isHovering, props }">
          <v-card v-if="!skills" class="thumbnails" v-bind="props" @click="skills = true">
            <v-img
              :aspect-ratio="9/16"
              cover
              :src="require('../assets/job.jpg')"
            >
              <v-expand-transition>
                <div
                  v-if="isHovering"
                  class="d-flex transition-fast-in-fast-out black-trans v-card--reveal text-h3 align-center justify-center text-shades-white"
                  style="height: 100%;"
                >
                <p style="font-size: 24px">
                  {{experience[1].time}}<br><i>{{experience[1].title}}<br>{{experience[1].title2}}</i>
                </p>
                </div>
              </v-expand-transition>
            </v-img>
          </v-card>
          <v-card elevation="6" v-if="skills" class="thumbnails" v-bind="props" @click="skills = false">
            <p style="font-size: 24px">{{experience[1].title}}</p>
            <p style="font-size: 24px">{{experience[1].title2}}</p>
            <p style="font-size: 20px"><i>{{experience[1].company}}</i></p>
            <p style="font-size: 20px; padding-bottom: 30px">{{experience[1].place}}</p>
            <v-divider style="padding-bottom: 30px" thickness="2"></v-divider>
            <ol density="compact" v-for="task of experience[1].tasks" :key="task" style="background: transparent; text-align: left; padding-left: 10px">
              <v-list-item density="compact" style="font-size: 18px" prepend-icon="mdi-vector-point">{{task}}</v-list-item>
            </ol>
          </v-card>
        </v-hover>
        </v-row>
      </v-col>
      <v-col>
        <v-row class="d-flex justify-center align-center">
        <v-hover v-slot="{ isHovering, props }">
          <v-card v-if="!language" class="thumbnails" v-bind="props" @click="language=true">
            <v-img
              :aspect-ratio="9/16"
              cover
              :src="require('../assets/skil.jpg')"
            >
              <v-expand-transition>
                <div
                  v-if="isHovering"
                  class="d-flex transition-fast-in-fast-out black-trans v-card--reveal text-h3 align-center justify-center text-shades-white"
                  style="height: 100%;"
                >
                <p style="font-size: 24px">
                  {{experience[2].time}}<br><i>{{experience[2].title}}</i>
                </p>
                </div>
              </v-expand-transition>
            </v-img>
          </v-card>
          <v-card elevation="6" v-if="language" class="thumbnails" v-bind="props" @click="language=false">
            <p style="font-size: 24px">{{experience[2].title}}</p>
            <p style="font-size: 20px"><i>{{experience[2].company}}</i></p>
            <p style="font-size: 20px; padding-bottom: 30px">{{experience[2].place}}</p>
            <v-divider style="padding-bottom: 30px" thickness="2"></v-divider>
            <ol density="compact" v-for="task of experience[2].tasks" :key="task" style="background: transparent; text-align: left; padding-left: 10px">
              <v-list-item density="compact" style="font-size: 18px" prepend-icon="mdi-vector-point">{{task}}</v-list-item>
            </ol>
          </v-card>
        </v-hover>
        </v-row>
      </v-col>
    </v-row>
    <v-row class="justify-center align-center" style="height: 5vw; padding-top: 100px">
      <p style="font-size: 28px; letter-spacing: 10px"><i>"I believe in hard work"</i></p>
    </v-row>
  </div>
</template>

<script>
export default {
  name: 'AboutMe',
  props: {
    msg: String
  },
  data(){
    return{
      language: false,
      aboutme: false,
      skills: false,
      experience:[
        {"time": "Nov 2016 - Nov 2019", "place": "Indonesia", "company": "Mondo Surf Village", "title": "Resort manager", "tasks": ["Manage overall operation, budgetary, and activities", "Recruite employees, and develop human resources", "Plan, evaluate, and improve the holiday programs", "Manage the staff", "Handle guests feedback"]},
        {"time": "April 2021 - Sept 2023", "place": "Germany", "company": "Ianeo solutions Gmbh", "title": "Working student", "title2": "(Software development)", "tasks": ["Develop front-end using VueJs, HTML, Javascript, and CSS", "Develop APIs","Integrate SQL database, back-end, and front-end code", "Develop back-end using NodeJs and PYTHON", "Debug and troubleshoot", "Maintain and clean code"]},
        {"time": "September 2023 - Now", "place": "Germany", "company": "Ianeo solutions Gmbh", "title": "Web/software developer", "tasks": ['Develop a web application','Develop backend using PHP', 'Develop plugins with Javascript', 'Develop front-end using HTML, CSS; and Twig', 'Learn new technology in Shopware']},
      ],
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.about-me-content {
  height: 60vh;
  /* padding-top: 25%;
  padding-bottom: 15%; */
  margin-bottom: 20px;
  margin-top: 50px;
  width: 50vw;
}
.bg-aboutme {
  /* background-image: url('../assets/bg3.jpg'); */
  background-size: cover;
}
.title {
  margin-top: 100px;
}
.thumbnails{
  margin: 5px;
  width: 370px;
  height: 500px;
  justify-content: center;
}
.thumb {
  width: 60%;
  /* height: 100px; */
}
.black-trans{
  background-color: black;
  opacity: 0.6;
  text-align: center;
}
@media screen and (min-width: 1150px) {
    .v-row.experience {
    padding-left: calc((100vw - 1150px)/2);
    padding-right: calc((100vw - 1150px)/2);
  }
}
</style>
