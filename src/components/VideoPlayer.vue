<template>
  <div>
    <video ref="video" loop muted playsinline :src="src" width="600"></video>
    <button @click="handleControlBtn">Play / Pause</button>
  </div>
</template>

<script setup lang="ts">
import { useGlobalEvent } from "@/composables/useGlobalEvent";
import { ref } from "vue";

defineProps({
  src: {
    type: String,
    required: true,
  },
});

const video = ref<HTMLVideoElement>();

function handleControlBtn() {
  video.value.paused ? video.value.play() : video.value.pause();
}

useGlobalEvent("keypress", (event) => {
  if (event.charCode !== 32) return;
  event.preventDefault();
  video.value.paused ? video.value.play() : video.value.pause();
});
</script>
<style scoped></style>
