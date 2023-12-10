<template>
<div id="home" class="bg">
<v-toolbar class="toolbar">
  <v-toolbar-items v-if="!small_screen">
    <v-btn v-for="item in items" :key="item.title"  @click="redirect($event, item.id)" flat>{{item.title}}</v-btn>
  </v-toolbar-items>
    <v-menu
      transition="slide-y-transition"
      v-if="small_screen"
    >
      <template v-slot:activator="{ props }">
        <v-btn
          v-bind="props"
          icon="mdi-menu"
        >
        </v-btn>
      </template>
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          @click="redirect($event, item.id)"
          class="menu_item"
        >
          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-menu>
</v-toolbar>
<v-row style="text-align: left; padding-left: 10%; width: fit-content">
  <v-col class="title">
    <p class="letter" style="font-family:vogue; transform: scale(.7, 1);">Hi...!</p>
    <p class="letter" style="font-family:vogue; transform: scale(.7, 1);">I'M BIRRU</p>
    <p class="letter" style="font-family:vogue; transform: scale(.7, 1);">PULTRONE</p>
  </v-col>
</v-row>
<v-row style="text-align: left; width: fit-content" class="welcome-row">
  <v-col>
    <p class="animated welcome" style="font-family:vogue">Junior Full-stack developer.</p>
  </v-col>
</v-row>
</div>
</template>

<script>

export default {
  name: 'HomePage',
  props: {
    msg: String
  },
  data(){
    return {
      small_screen: false,
      widthWindow: 0,
      heightWindow: 0,
      items: [{'title': 'Home', 'id': '#home'}, {'title': 'About Me', 'id': '#about-me'}, {'title': 'Education', 'id': '#my-education'}, {'title': 'Experience', 'id': '#my-experience'}, {'title': 'Projects', 'id': '#my-project'}, {'title': 'Hire Me', 'id': 'mailto:birru.hayyu@gmail.com'}, {'title': 'Download CV', 'id': '../files/CV_Birru.pdf'}]
    }
  },
  unmounted() {
    window.removeEventListener("resize", this.resizeWeb);
  },
  mounted(){
    this.resizeWeb();
    window.addEventListener("resize", this.resizeWeb);
  },
  methods:{
    redirect(e, div){
      if (div == '#home' || div == '#my-experience' ){
        window.location.href = div;
        window.location.reload();
      } else{
        window.location.href = div;
      }
      // e.preventDefault();
      // e.stopPropagation(); 
    },
    mailTo(){
      location.href='mailto:birru.hayyu@gmail.com';
    },
    resizeWeb(){
      this.widthWindow = window.innerWidth;
      this.heightWindow = window.innerHeight;
      if (this.widthWindow < 900){
        this.small_screen = true;
      } else {
        this.small_screen = false;
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
  background-image: url('../assets/cup2.jpg');
  background-size: cover;
  width: 100% !important;
  height: 100vh;
  /* min-height: 100vh; */
  /* max-height: 750px; */
  background-position: center center;
  padding: 0px;
}
.title {
  padding-top: 30vh;
 text-align: left;
   display: inline-block;
   justify-content: left;
}
.toolbar {
  background-color: white;
  position: fixed;
  height: 60px;
  z-index: 1000;
}
.animated{
  border-right: 5px solid;
  width: 100%;
  white-space: nowrap;
  overflow: hidden;
  animation: 
  typing 3s steps(31),
  cursor .4s step-end infinite alternate;
}
@keyframes cursor{
  50% { border-color: transparent}
}

@keyframes typing{
  from { width: 0}
}
.menu_item:hover{
  background-color: "primary";
  opacity: 0.6;
}
</style>
