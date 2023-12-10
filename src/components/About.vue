<template>
<v-container style="max-height: fit-content;padding-top:100px;">
  <v-row>
    <v-col>
      <v-row class="justify-center align-center"> 
        <p class="about" style="transform: scale(.7, 1);font-family:vogue">About Me</p>
        <v-carousel
          hide-delimiters
          progress="warning"
          show-arrows
          style="width: fit-content; height: fit-content; min-height: 500px"
        >
          <v-carousel-item
            v-for="(slide, i) in slides"
            :key="i"
            width="500"
          >
            <v-sheet
              height="fit-content"
              width="fit-content"
              style="margin-left:100px;margin-right:100px; background: transparent; margin-top: 50px"
            >
              <div class="fill-height justify-center align-center">
                <div class="text-h4" style="text-align:left" v-if="slide[0] != ''">
                  {{ slide[0] }}<br><br>
                </div>
                <div class="text-h5" style="text-align:left" v-for="i of slide[1].split(';')" :key="i">
                  <div v-if="!checkList(i)"><i>{{i}}</i></div>
                  <div v-if="checkList(i)">
                      <b><i>{{i.split(':')[0]}}</i>:</b><i>{{i.split(':')[1]}}</i>&nbsp;
                  </div>
                </div>
              </div>
            </v-sheet>
          </v-carousel-item>
        </v-carousel>
    </v-row>  
    </v-col>
    <v-col>
      <!-- <v-row style="height: 200px"><v-col></v-col></v-row> -->
      <v-row>
        <v-col cols="2"></v-col>
        <v-col cols="8" style="display: flex">
      <v-img
        :src="require('../assets/new4.jpg')"
        class="my-pic"
      >
      </v-img>
        </v-col>
        <v-col cols="2"></v-col>
      </v-row>
    </v-col>
  </v-row> 
  </v-container>
</template>


<script>
export default {
  name: 'AboutYou',
  props: {
    msg: String
  },
  data() {
    return {
        slides: [
        ["", '"When I discovered coding, I fell in love instantly. I had never experienced being in the state flow like I do when I am coding. Therefore, although I have a long history in academic research and management in tourism, I have taken the necessary steps to become a software developer.;"'],
        ["Bio", '"I was born in a small city called Jember in Indonesia, on August 29, 1991. Growing up in a village, I had spent much time in the nature. Besides that, I also had always liked solving puzzles and reading detective books."'],
        ["Acquired skills", "Javascript - Python - NodeJS; VueJS - HTML - CSS; SQL - Git - PHP - Twig; MongoDB - Wordpress"],
        ["I speak", "Indonesian - Native;English - Advanced;German - B1"],
        ],
    }
  },
  methods:{
    checkList(text){
        if (text.split(':').length > 1){
            return true;
        } else {
            return false;
        }
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
.bg {
  background-image: url('../assets/edu2.jpg');
  background-size: cover;
  background-position: center center;
  /* min-height: 100vh; */
  height: fit-content;
}
/* .v-img__img--contain{
  object-fit:fill;
} */
.black-trans{
  background-color: black;
  opacity: 0.5;
  height: 330px;
  width: 100%;
  text-align: center;
  /* overflow-y: auto; */
  /* margin-left: 10%;
  margin-right: 10%; */
}
.list--dense.fix .list__tile__title {
  height: 10px;
}
.bg {
    background-size: cover;
  /* min-height: 100vh;  */
  height: fit-content;
}
.v-row{
  margin: 0px;
}
/* @media screen and (max-width: 500px) {
  div {
    font-size: 5vw;
  }
  p.letter {
    font-size: 20vw;
  }
} */



</style>
