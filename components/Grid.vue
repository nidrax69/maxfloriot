<template>
  <Flicking :options="{ circular: true, horizontal: true, gap: 10 }" :plugins="plugins">
    <div class="col">
      <img :src="require('~/assets/img/' + repository +'/1.JPG')" class="photo" alt="" />
    </div>
    <div class="col">
      <img :src="require('~/assets/img/' + repository +'/3.JPG')" class="photo" alt="" />
    </div>
    <div class="col">
      <img :src="require('~/assets/img/' + repository +'/2.JPG')" class="photo" alt="" />
    </div>
    <div class="col">
      <img :src="require('~/assets/img/' + repository +'/4.JPG')" class="photo" alt="" />
    </div>
    <div class="col">
      <img :src="require('~/assets/img/' + repository +'/5.JPG')" class="photo" alt="" />
    </div>
    <div class="col">
      <img :src="require('~/assets/img/' + repository +'/6.JPG')" class="photo" alt="" />
    </div>
  </Flicking>
</template>

<script>
import {  Parallax } from "@egjs/flicking-plugins";
export default {
  props: {
    repository: {
      default: 'animals',
      type: String
    }
  },
  data: () => ({
    plugins: [new Parallax("img", 4)]
  }),
};
</script>
<style>
.photo {
  width: 600px;
}
</style>
