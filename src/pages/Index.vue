<template>
  <div class="q-pa-md bg-black">
    <q-parallax>
      <template v-slot:media>
        <video
          class="videobanner"
          poster="~assets/pokeball.png"
          autoplay
          loop
          muted
        >
          <source type="video/webm" src="~assets/video_webm.webm" />
          <source type="video/mp4" src="~assets/video_index.mp4" />
        </video>
      </template>
      <!-- <h3 class="text-white">Video</h3> -->
    </q-parallax>
  </div>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "PageIndex",
});
</script>
<style >
.videobanner {
  width: 100% !important;
  height: 100% !important;
  /* filter: blur(2px); */
}
</style>