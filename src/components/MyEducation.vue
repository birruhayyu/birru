
<template>
<div  id="my-education" >
    <v-row class="justify-center align-center" style="width: 100%; padding-top: 80px">
      <p style="font-size: 24px; letter-spacing: 10px; width: fit-content"><i>"Contentment is my goal.<br>Curiosity is my drive.<br>Learning is my tool."</i></p>
    </v-row>
    </div>
<!-- <div class="justify-center align-center d-flex" >
  </div> -->
<v-row class="justify-center align-center d-flex" style="padding-top: 80px; margin-bottom: 100px">
<v-col>
  <v-row class="justify-center align-center">
    <h2 style="font-size: 100px;transform: scale(.7, 1); color:primary; font-family:vogue; width: fit-content" class="title">EDUCATION</h2>
    <v-icon size="100">mdi-school</v-icon>
  </v-row>
</v-col>
<v-col>
  <v-row class="edu-list"> 
  <v-timeline side="end">
      <v-timeline-item
        v-for="item in items"
        :key="item.id"
        :dot-color="item.color"
        size="small"
      >
        <v-alert
          :value="true"
          class="edu"
        >
        <p>{{item.time}}</p>
        <v-divider :color="item.color" style="opacity: 1;" thickness="1"></v-divider>
        <p>{{item.school}}</p>
        <p>{{item.place}}</p>
        <p>{{item.title}}</p>
        </v-alert>
      </v-timeline-item>
    </v-timeline>
  </v-row>
</v-col>
</v-row>
</template>

<script>
export default {
  name: 'MyEducation',
  props: {
    msg: String
  },
  data() {
    return {
      education:[
        {"time": "July 2009 - August 2013", "place": "Jakarta, Indonesia", "school": "University of Indonesia", "title": "Bachelor of Psychology"},
        {"time": "September 2014 - February 2016", "place": "Bristol, UK", "school": "University of Bristol", "title": "M.Ed. Educational Policy and Development"},
        {"time": "October 2020 - September 2023", "place": "Saarbrücken, Germany", "school": "Universität des Saarlandes", "title": "M.Sc. Educational Technology"},
      ],
      items: [
        {
          id: 1,
          color: 'warning',
          icon: 'mdi-information',
          time: 'July 2009 - August 2013',
          place: "Jakarta, Indonesia", 
          school: "University of Indonesia", 
          title: "Bachelor of Psychology"
        },
        {
          id: 2,
          color: '#2C3E50',
          icon: 'mdi-alert-circle',
          time: "September 2014 - February 2016",
          place: "Bristol, UK", 
          school: "University of Bristol", 
          title: "M.Ed. Educational Policy and Development"
        },
        {
          id: 3,
          color: 'warning',
          icon: 'mdi-information',
          time: "October 2020 - September 2023",
          place: "Saarbrücken, Germany", 
          school: "Universität des Saarlandes", 
          title: "M.Sc. Educational Technology"
        },
      ],
      isAnimated: false
    }
  },
  mounted(){
    if (window.innerWidth >= 1400){
      this.isAnimated = true;
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
  width: 100% !important;
  height: 100vh;
  max-height: fit-content;
  /* min-height: 100vh; */
  /* max-height: 750px; */
  background-position: center center;
  padding: 0px;
}
.button {
  margin-top: 35vh;
}
.thumbnails{
  width: 100%;
  min-width: 360px;
  min-height: 30vh;
  max-height: fit-content;
  justify-content: center;
  border: 5px solid #f0ad4e;
  margin-left : 30px;
  margin-right: 30px;
  padding: 20px;
}
.box{
  display: flex;
}
@media screen and (min-width: 1100px){
  .edu-list {
    align-content: left;
    justify-content: left;
  }
}
@media screen and (max-width: 1100px){
  .edu-list {
    align-content: center;
    justify-content: center;
  }
}
.v-row {
  margin: 0px;
}
</style>
