<template>
  <div class="bg-yellow-lighten-1 text-center d-flex flex-column" style="padding-top: 30px; padding-bottom: 50px">
    <div>
      <v-btn v-for="[icon, link] in icons" :key="icon" class="mx-4" :icon="icon" variant="text" :href="link"></v-btn>
    </div>
  </div>
</template>

<script>
export default {
  name: 'MyFooter',
  data() {
    return {
      icons: [
        ['mdi-email', 'mailto:birru.hayyu@gmail.com'],
        ['mdi-linkedin', 'https://www.linkedin.com/in/birru-hayyu-278a6451/'],
        ['mdi-github', 'https://github.com/birruhayyu']
      ],
    };
  },
};
</script>
<style scoped>

</style>