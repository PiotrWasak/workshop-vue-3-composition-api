<template>
  <div id="app">
    <HelloWorld msg="Rick & Morty Characters" />
    <VideoPlayer style="width: 800px; margin: 0 auto" src="/puppiness.mp4"></VideoPlayer>
  </div>
</template>

<script setup>
import HelloWorld from "@/components/HelloWorld.vue";
import VideoPlayer from "./components/VideoPlayer.vue";
</script>
