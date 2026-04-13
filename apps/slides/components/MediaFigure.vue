<script setup lang="ts">
import { computed, ref } from 'vue'

const props = withDefaults(defineProps<{
  src: string
  alt?: string
  width?: string
  height?: string
}>(), {
  alt: 'Slide figure',
  width: '1100px',
  height: '620px',
})

const failed = ref(false)

const shellStyle = computed(() => ({
  maxWidth: props.width,
  minHeight: props.height,
}))
</script>

<template>
  <div class="media-figure" :style="shellStyle">
    <img
      v-if="!failed"
      class="media-figure__image"
      :src="src"
      :alt="alt"
      @error="failed = true"
    >
    <div v-else class="media-figure__placeholder">
      <div class="media-figure__kicker">Replace asset</div>
      <code>{{ src }}</code>
    </div>
  </div>
</template>

<style scoped>
.media-figure {
  width: min(100%, v-bind('props.width'));
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto;
}

.media-figure__image,
.media-figure__placeholder {
  width: 100%;
  min-height: v-bind('props.height');
  border-radius: 20px;
}

.media-figure__image {
  object-fit: contain;
  border: 1px solid rgba(255, 255, 255, 0.06);
  box-shadow: 0 30px 90px rgba(0, 0, 0, 0.35);
}

.media-figure__placeholder {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 14px;
  padding: 24px;
  background: linear-gradient(180deg, rgba(106, 176, 255, 0.08), rgba(143, 240, 164, 0.04));
  border: 1px dashed #25303b;
  color: #9da7b3;
  text-align: center;
}

.media-figure__placeholder code {
  max-width: 100%;
  overflow-wrap: anywhere;
}

.media-figure__kicker {
  color: #8ff0a4;
  font-family: 'JetBrains Mono', monospace;
  font-size: 14px;
  letter-spacing: 0.08em;
  text-transform: uppercase;
}
</style>
