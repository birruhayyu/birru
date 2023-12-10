<template>
  <HomePage id="home" class="section"/>
  <AboutYou id="about-me" class="section"/>
  <MyEducation class="section-half"/>
  <MyExperience class="section"/>
  <MyProjects id="my-project"/>
  <MyFooter/>
</template>

<script>
import HomePage from './components/HomePage.vue'
import MyEducation from './components/MyEducation.vue'
import MyExperience from './components/MyExperience.vue'
import MyProjects from './components/MyProjects.vue'
import AboutYou from './components/About.vue'
import MyFooter from './components/MyFooter.vue'

export default {
  name: 'App',
  components: {
    // HelloWorld,
    HomePage,
    // AboutMe,
    MyEducation,
    MyExperience,
    MyProjects,
    AboutYou,
    MyFooter
    // HireMe
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* margin-top: 60px; */
}

.propic {
  width: 200px;
  border-radius: 50%;
  margin-top: 30px;
  margin-bottom: 30px;
}

/* .section {
  min-height: 100vh;
} */
.section-half {
  height: 70vh;
}
.animated{
  border-right: 5px solid;
  width: 100%;
  white-space: nowrap;
  overflow: hidden;
  animation: 
    typing 4s steps(31),
    cursor .4s step-end infinite alternate;
}
@keyframes cursor{
  50% { border-color: transparent}
}

@keyframes typing{
  from { width: 0}
}

@media screen and (max-width: 530px) {
  div {
    font-size: 4vw;
    width: 100%;
  }
  p.letter {
    font-size: 15vw;
    max-height: 60px;
  }
  p.about {
    font-size: 20vw;
  }
  .v-row.welcome-row {
    margin-left: 17%;
  }
  .v-alert.edu {
    font-size: 3vw;
  }
  h2.title {
    font-size: 30vw;
  }
}
@media screen and (min-width: 530px) and (max-width: 900px) {
  p.letter {
    font-size: 7vw;
    max-height: 50px;
  }
  p.welcome {
    font-size: 4vw;
  }
  p.about {
    font-size: 9vw;
  }
  .v-row.welcome-row {
    margin-left: 13%;
  }
  .v-img.my-pic {
    width: 360px;
  }
  .v-alert.edu {
    width: 500px;
  }
}

@media screen and (min-width: 900px) {
  p.letter {
    font-size: 5vw;
    max-height: 85px;
  }
  p.welcome {
    font-size: 2vw;
  }
  p.about {
    font-size: 7vw;
  }
  .v-row.welcome-row {
    margin-left: 13%;
  }
  .v-alert.edu {
    width: 500px;
    font-size: 22px;
  }
}
@media screen and (min-width: 890px) {
    .v-img.my-pic {
    min-width: 358px;
    max-width: 450px;
    padding-top: 30%;
  }
}

#scroll-container {
  /* border: 3px solid black;
  border-radius: 5px; */
  overflow: hidden;
}

#scroll-text {
  text-align: right;

  /* animation properties */
  -moz-transform: translateX(100%);
  -webkit-transform: translateX(100%);
  transform: translateX(-100%);
  
  -moz-animation: my-animation 15s linear infinite;
  -webkit-animation: my-animation 15s linear infinite;
  animation: my-animation 15s linear infinite;
}

/* for Firefox */
@-moz-keyframes my-animation {
  from { -moz-transform: translateX(100%); }
  to { -moz-transform: translateX(-100%); }
}

/* for Chrome */
@-webkit-keyframes my-animation {
  from { -webkit-transform: translateX(100%); }
  to { -webkit-transform: translateX(-100%); }
}

@keyframes my-animation {
  from {
    -moz-transform: translateX(100%);
    -webkit-transform: translateX(100%);
    transform: translateX(100%);
  }
  to {
    -moz-transform: translateX(-100%);
    -webkit-transform: translateX(-100%);
    transform: translateX(-100%);
  }
}
</style>
