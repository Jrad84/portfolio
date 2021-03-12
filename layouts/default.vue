<template>
 <v-app>
 
      <AppBar />
  <!-- <v-main> -->
   <!-- <video autoplay playsinline muted loop id="myVideo">
        <source
          src="~/assets/wolf_background.mp4"
          type="video/mp4"
        />
      </video> -->
    
  <div>
   <nuxt />
  </div>

</v-app>

</template>

<script>
import AppBar from "~/components/AppBar.vue";
export default {
  components: {AppBar}
}
</script>
<style scoped>
#myVideo {
  position: fixed;
  right: 0;
  bottom: 0;
  min-width: 100%;
  min-height: 100%;
  /* z-index: -1; */
}
</style>
