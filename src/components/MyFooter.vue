<template>
  <div
    class="bg-yellow-lighten-1 text-center d-flex flex-column"
    style="padding-top: 30px; padding-bottom: 50px"
  >
    <div>
      <v-btn
        v-for="icon in icons"
        :key="icon[0]"
        class="mx-4"
        :icon="icon[0]"
        variant="text"
        :href="icon[1]"
      ></v-btn>
    </div>

    <!-- <div class="pt-0">
      Special thanks to the amazing photos taken by: Leone Venter, Victor Freitas, Bermix Studio, Myriam Jessier, Ivan Shilov, Aaron Weiss, Clément Hélardot, Olia Gozha, and charlesdeluvio on Unsplash.
    </div> -->

  </div>
</template>
<script>
  export default {
    name: 'MyFooter',
    data: () => ({
      icons: [
        ['mdi-email', 'mailto:birru.hayyu@gmail.com'],
        ['mdi-linkedin', 'https://www.linkedin.com/in/birru-hayyu-278a6451/'],
        ['mdi-github', 'https://github.com/birruhayyu']
      ],
    }),
  }
</script>
<style scoped>

</style>