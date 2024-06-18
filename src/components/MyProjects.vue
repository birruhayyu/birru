<template>
 <v-container>
  <v-row style="margin-top: 60px; margin-bottom: 30px">
    <v-col>
      <div class="bg justify-center align-center">
        <p style="transform: scale(.7, 1); color:primary; font-family:vogue; width: fit-content; padding-left: 50px; padding-right: 50px" class="pic-ani about">PROJECTS</p>
      </div>
    </v-col>
  </v-row>
  <v-row class="d-flex justify-center align-center margin-remove">
    <v-col cols="4" :class="{box: !isSmall, small: isSmall}">
      <v-img :src="require('../assets/language_app.jpg')" style="object-fit:cover; width: 100%; height: 100%" cover>
      <div class="attribution" style="opacity: 0.7;color: white">
        Photo by <a style="color: white; text-decoration: none" href="https://unsplash.com/@leookubo?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Leonardo Toshiro Okubo</a> on <a style="color: white; text-decoration: none" href="https://unsplash.com/photos/unknown-person-writing-on-chalkboard-jBSTNenQxok?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Unsplash</a>
      </div>
      </v-img>
    </v-col>
    <v-col cols="4" class="box">
      <v-sheet elevation="2" style="width: 100%; height: 100%; padding:15px">
        <v-list-item-title class="project-title">{{projects[3].title}}</v-list-item-title>
        <v-divider></v-divider>
        <p style="padding: 10px">{{projects[3].project}}<a href="https://github.com/birruhayyu/german_language_app">here</a>.</p>
        <p><b>Technology/Language: </b> {{projects[3].technology}}</p> 
      </v-sheet>
    </v-col>
  </v-row>
  <v-row class="d-flex justify-center align-center margin-remove">
    <v-col cols="4" class="small" v-if="isSmall">
      <v-img :src="require('../assets/data2.jpg')" style="object-fit:cover; width: 100%; height: 100%" :class="{small: isSmall}">
      <div class="attribution" style="opacity: 0.7; color: white">
        Photo by <a style="color: black; text-decoration: none" href="https://unsplash.com/@mjessier?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Myriam Jessier</a> on <a style="color: black; text-decoration: none" href="https://unsplash.com/photos/person-using-macbook-pro-on-black-table-eveI7MOcSmw?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Unsplash</a>
      </div>
      </v-img>
    </v-col>
    <v-col cols="4" class="box">
      <v-sheet elevation="2" style="width: 100%; height: 100%; padding:15px">
        <v-list-item-title class="project-title">{{projects[0].title}}</v-list-item-title>
        <v-divider></v-divider>
        <p style="padding: 10px">{{projects[0].project}}</p>
        <p><b>Technology/Language: </b> {{projects[0].technology}}</p> 
      </v-sheet>
    </v-col>
    <v-col cols="4" class="box" v-if="!isSmall">
      <v-img :src="require('../assets/data2.jpg')" style="object-fit:cover; width: 100%; height: 100%" cover>
      <div class="attribution" style="opacity: 0.7; color: black">
        Photo by <a style="color: black; text-decoration: none" href="https://unsplash.com/@mjessier?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Myriam Jessier</a> on <a style="color: black; text-decoration: none" href="https://unsplash.com/photos/person-using-macbook-pro-on-black-table-eveI7MOcSmw?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Unsplash</a>
      </div>
      </v-img>
    </v-col>
  </v-row>
  <v-row class="d-flex justify-center align-center margin-remove">
    <v-col cols="4" :class="{box: !isSmall, small: isSmall}">
      <v-img :src="require('../assets/excalibur.jpg')" style="object-fit:cover; width: 100%; height: 100%" cover>
      <div class="attribution" style="opacity: 0.7; color: black">
      Photo by <a style="color: black; text-decoration: none" href="https://unsplash.com/@bermixstudio?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Bermix Studio</a> on <a style="color: black; text-decoration: none" href="https://unsplash.com/photos/a-phone-with-a-stethoscope-on-top-of-it-l8uCymHXI-g?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Unsplash</a>
      </div>
      </v-img>
    </v-col>
    <v-col cols="4" class="box">
      <v-sheet elevation="2" style="width: 100%; height: 100%; padding:15px">
        <v-list-item-title class="project-title">{{projects[1].title}}</v-list-item-title>
        <v-divider></v-divider>
        <p style="padding: 10px">{{projects[1].project}}</p>
        <p><b>Technology/Language: </b> {{projects[1].technology}}</p> 
      </v-sheet>
    </v-col>
  </v-row>
  <v-row class="d-flex justify-center align-center margin-remove">
    <!-- <v-col cols="4" class="small" v-if="isSmall">
      <v-img :src="require('../assets/training_app.jpg')" style="object-fit:cover; width: 100%; height: 100%" :class="{small: isSmall}">
      <div class="attribution" style="opacity: 0.7; color: white">
       Photo by <a style="color: black; text-decoration: none" href="https://unsplash.com/@bermixstudio?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Bermix Studio</a> on <a style="color: black; text-decoration: none" href="https://unsplash.com/photos/a-phone-with-a-stethoscope-on-top-of-it-l8uCymHXI-g?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Unsplash</a>
      </div>
      </v-img>
    </v-col> -->
    <v-col cols="4" class="box">
      <v-sheet elevation="2" style="width: 100%; height: 100%; padding:15px">
        <v-list-item-title class="project-title">{{projects[2].title}}</v-list-item-title>
        <v-divider></v-divider>
        <p style="padding: 10px">{{projects[2].project}}<a href="https://github.com/birruhayyu/training_app_api">here</a>.</p>
        <p><b>Technology/Language: </b> {{projects[2].technology}}</p> 
      </v-sheet>
    </v-col>
    <!-- <v-col cols="4" class="box" v-if="!isSmall">
      <v-img :src="require('../assets/training_app.jpg')" style="object-fit:cover; width: 100%; height: 100%" cover>
      <div class="attribution" style="opacity: 0.7; color: white">
        Photo by <a style="color: white; text-decoration: none" href="https://unsplash.com/@victorfreitas?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Victor Freitas</a> on <a style="color:white; text-decoration: none" href="https://unsplash.com/photos/person-locking-gym-plates-on-barbell-KIzBvHNe7hY?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Unsplash</a>
      </div> 
      </v-img>
    </v-col> -->
  </v-row>
 </v-container> 
</template>

<script>
export default {
  name: 'MyProjects',
  props: {
    msg: String
  },
  data() {
    return {
      projects:[
        {"title": "Data quality management system", "project": "My second project with the team during my part-time work at Ianeo Gmbh is building a data management system. This application checks and maintains data quality on the client’s system. For example, our application checks if there is any anomaly in the database before the data is shown on the front-end.", "technology": "NodeJS, Javascript, VueJS, HTML, CSS, MySQL, Git"},
        {"title": "Excalibur project", "project": "Excalibur is my first project when I was working part-time at Ianeo Solutions GmbH, Germany. This app was built to troubleshoot customers’ internet connection issues for our client, Telefonica Germany. I was working on both on backend and frontend.", "technology": "Python, Javascript, HTML, CSS, Apache, Git"},
        {"title": "Training App", "project": "I am currently developing a personal training app. In this app, I want to be able to schedule my monthly training programs. The app already contains several default training programs based on the training goals. Each training program has more detailed information about the training itself. User can also add customized training program. Progress can be found ", "technology": "NodeJS, Javascript, VueJS, MongoDB"},
        {"title": "Language App", "project": "My german-english language app is my first python project that I built to fulfill my programming course during my study at uni. It has several features, such as translation, simple grammars, games, and learning analytics. The whole project can be found ", "technology": "Python, Github"}
      ],
      open: false,
      data: false,
      lang: false,
      excalibur: false,
      train: false,
      isSmall: false
    }
  },
  mounted(){
    if (window.innerWidth < 820){
      this.isSmall = true;
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

.v-img__img--contain {
  object-fit: cover;
}

.project-title {
  padding-top: 20px;
  padding-bottom: 20px;
  font-size: 22px;
  font-style:oblique;
}

.bg {
  height: 200px;
}
.box {
  height: 400px; 
  min-width: 400px; 
  padding: 0px;
}
.small {
  height: 100%;
  min-width: 400px; 
  padding: 0px;
  
}

</style>
<style>

.pic-ani {
    position: relative;
    margin: auto;
    width: 160px;
    line-height: 160px;
    text-align: center;
    font-size: 24px;
    
}
.pic-ani::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  border: 5px solid #f0ad4e;
  transition: all .5s;
  animation: clippath 4s infinite linear;
}

@keyframes clippath {
    0%,
    100% {
        clip-path: inset(0 0 95% 0);
    }
    
    25% {
        clip-path: inset(0 95% 0 0);
    }
    50% {
        clip-path: inset(95% 0 0 0);
    }
    75% {
        clip-path: inset(0 0 0 95%);
    }
}
.v-row.margin-remove {
  margin: 0px;
}
</style>
