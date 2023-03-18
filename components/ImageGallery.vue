<template>
  <v-card class="mx-10 my-5 pa-3">
<v-row >
<v-col v-for="n in 200"  :key="n" cols="12" md="4" sm="6" lg="2">
  <v-hover v-slot="{ isHovering,props}">
  <v-card
      :elevation=" 2"
      :class="{ 'on-hover': isHovering }"
      v-bind="props"
      @click="copyUrl(`https://picsum.photos/10/6?image=${n * 5 + 10}${p.isWithColor ? '':'&grayscale'}`)"
  >
    <v-img
        aspect-ratio="1"
        cover
        :lazy-src="`https://picsum.photos/10/6?image=${n * 5 + 10}${p.isWithColor ? '':'&grayscale'}`"
    :src="`https://picsum.photos/600/300?image=${n * 5 + 10}${p.isWithColor ? '':'&grayscale'}`"
    >
      <template v-slot:placeholder>
        <v-row
            class="fill-height ma-0"
            align="center"
            justify="center">
          <v-progress-circular
              indeterminate
              color="grey-lighten-5"
          ></v-progress-circular>
        </v-row>

      </template>
    </v-img>

  </v-card>
  </v-hover>
</v-col>
</v-row>
  </v-card>
</template>

<script setup>
import {defineProps} from 'vue'
const p=defineProps(['isWithColor'])
const copyUrl=async (url)=>{
  await navigator.clipboard.writeText(url)
}

</script>

<style scoped>
.v-card {

  transform: scale(1);

  transition: transform  .4s   ease-in-out ;
}

.v-card:not(.on-hover) {
  z-index: 0;
 transform: scale(1);
}
.v-card .on-hover{

  transform: scale(1.2) translate(0px,20px);
  z-index: 10;
}
</style>