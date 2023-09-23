<template>
  <v-app class="wrap">
    <v-img src="@/assets/background_main.png" class="bg" cover />
    <default-view class="content" />
  </v-app>
</template>

<script setup>
import DefaultView from "./View.vue";
</script>

<style scoped>
.wrap {
  position: relative;
}

.bg {
  position: absolute;
  left: 0;
  top: 0;
  height: auto;
  width: 100%;
  opacity: 0.8;
}

.content {
  position: relative;
}
</style>

<style>
html {
  overflow-y: auto;
}
</style>
