<template>
<v-navigation-drawer  expand-on-hover rail
                     image="https://cdn.vuetifyjs.com/images/backgrounds/bg-2.jpg"
>
  <v-list>
    <v-list-item
        title="Saliou Bailo Bah"
        value="saliou"
    >


    </v-list-item>
  </v-list>
  <v-divider></v-divider>
  <v-list density="compact" nav>
    <v-list-item prepend-icon="mdi-image"  title="Color Gallery" value="color" @click="selectOption(true)">

    </v-list-item>
    <v-list-item prepend-icon="mdi-dialpad" title="GrayScale Gallery" value="color" @click="selectOption(false)"/>
  </v-list>
</v-navigation-drawer>
</template>

<script setup>
import {defineEmits } from 'vue'
const emit=defineEmits(['selectOption'])

const selectOption=(isColor)=>{
  emit("selectOption",isColor)
}
</script>

<style scoped>

</style>