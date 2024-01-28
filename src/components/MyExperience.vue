<template>
  <div id="my-experience">
    <p id="scroll-text" class="scroll-ani" style="color: grey;">EXPERIENCE</p>
  </div>
  <div style="max-height: fit-content; width: 100%">
    <v-row class="d-flex justify-center align-center experience" style="width: fit-content">
      <v-col v-for="(item, index) in experience" :key="index">
        <v-hover v-slot="{ isHovering, props }">
          <v-card v-if="!selectedCard(index)" class="thumbnails" v-bind="props" @click="selectCard(index)">
            <v-img :aspect-ratio="9/16" cover :src="require(`../assets/${item.image}`)">
              <v-expand-transition>
                <div v-if="isHovering || isSmall" class="d-flex transition-fast-in-fast-out black-trans v-card--reveal text-h3 align-center justify-center text-shades-white" style="height: 100%">
                  <p style="font-size: 24px">{{ item.time }}<br><i>{{ item.title }}<br>{{ item.title2 ? `${item.title2}` : '' }}</i></p>
                </div>
              </v-expand-transition>
              <div class="attribution" style="color: white; opacity: 0.7">
                Photo by <a :style="{ color: 'white', textDecoration: 'none' }" :href="item.photoCredit.link">{{ item.photoCredit.name }}</a> on <a :style="{ color: 'white', textDecoration: 'none' }" :href="item.photoCredit.photoLink">Unsplash</a>
              </div>
            </v-img>
          </v-card>
          <v-card elevation="6" v-if="selectedCard(index)" class="thumbnails" v-bind="props" @click="deselectCard(index)" style="padding: 5px">
            <p style="font-size: 24px">{{ item.title }}</p>
            <p style="font-size: 24px">{{ item.title2 ? item.title2 : '' }}</p>
            <p style="font-size: 20px"><i>{{ item.company }}</i></p>
            <p style="font-size: 20px; padding-bottom: 30px">{{ item.place }}</p>
            <v-divider style="padding-bottom: 30px" thickness="2"></v-divider>
            <ol density="compact" v-for="task in item.tasks" :key="task" style="background: transparent; text-align: left; padding-left: 10px">
              <v-list-item density="compact" style="font-size: 18px" prepend-icon="mdi-vector-point">{{ task }}</v-list-item>
            </ol>
          </v-card>
        </v-hover>
      </v-col>
    </v-row>
    <v-row class="justify-center align-center" style="height: 5vw; padding-top: 100px; padding-bottom: 80px">
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
  data() {
    return {
      selectedCardIndex: null,
      experience: [
        { "time": "Nov 2016 - Nov 2019", "place": "Indonesia", "company": "Mondo Surf Village", "title": "Resort manager", "title2": null, "tasks": ["Manage overall operation, budgetary, and activities", "Recruit employees, and develop human resources", "Plan, evaluate, and improve the holiday programs", "Manage the staff", "Handle guests feedback"], "image": "me.jpg", "photoCredit": { name: "Aaron Weiss", link: "https://unsplash.com/@aaronweiss?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash", photoLink: "https://unsplash.com/photos/woman-in-sweater-sits-on-green-boat-on-dock-8bUnDiV2aJg?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash" } },
        { "time": "April 2021 - Sept 2023", "place": "Germany", "company": "Ianeo solutions Gmbh", "title": "Working student", "title2": "(Software development)", "tasks": ["Develop front-end using VueJs, HTML, Javascript, and CSS", "Develop APIs", "Integrate SQL database, back-end, and front-end code", "Develop back-end using NodeJs and PYTHON", "Debug and troubleshoot", "Maintain and clean code"], "image": "job.jpg", "photoCredit": { name: "Clément Hélardot", link: "https://unsplash.com/@clemhlrdt?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash", photoLink: "https://unsplash.com/photos/black-and-silver-laptop-computer-on-table-95YRwf6CNw8?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash" } },
        { "time": "September 2023 - Now", "place": "Germany", "company": "Ianeo solutions Gmbh", "title": "Web/software developer", "title2": null, "tasks": ['Develop a web application', 'Develop backend using PHP', 'Develop plugins with Javascript', 'Develop front-end using HTML, CSS; and Twig', 'Learn new technology in Shopware'], "image": "skil.jpg", "photoCredit": { name: "charlesdeluvio", link: "https://unsplash.com/@charlesdeluvio?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash", photoLink: "https://unsplash.com/photos/black-and-gray-laptop-computer-HTDVSbFsy3U?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash" } },
      ],
      isSmall: false,
    };
  },
  computed: {
    isSmallScreen() {
      return window.innerWidth < 900;
    },
  },
  methods: {
    selectedCard(index) {
      return this.selectedCardIndex === index;
    },
    selectCard(index) {
      this.selectedCardIndex = index;
    },
    deselectCard() {
      this.selectedCardIndex = null;
    },
  },
  mounted() {
    window.addEventListener('resize', this.resizeWeb);
    this.isSmall = this.isSmallScreen;
  },
  unmounted() {
    window.removeEventListener('resize', this.resizeWeb);
  },
  resizeWeb() {
    this.isSmall = this.isSmallScreen;
  },
};
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
@media screen and (min-width: 1212px) {
    .v-row.experience {
    padding-left: calc((100vw - 1212px)/2);
    /* padding-right: calc((100vw - 1150px)/2); */
  }
}
@media screen and (max-width: 450px) {
    .v-col {
    padding-left: 0;
    padding-right: 0;
  }
  .thumbnails {
    margin: 0;
  }
}
.v-row{
  margin: 0px;
}
</style>
