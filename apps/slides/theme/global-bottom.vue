<script setup lang="ts">
import { ref } from 'vue'

const logoError = ref(false)
</script>

<template>
  <footer class="deck-footer">
    <div class="deck-footer-left">
      𝕏 {{ $slidev.themeConfigs.handle || '@santychuy_dev' }}
    </div>
    <div class="deck-footer-center">
      {{ String($nav.currentPage).padStart(2, '0') }} / {{ String($nav.total).padStart(2, '0') }}
    </div>
    <div class="deck-footer-right">
      <img
        v-if="!logoError"
        class="deck-logo"
        :src="$slidev.themeConfigs.logo || '/branding/logo.png'"
        alt="Brand logo"
        @error="logoError = true"
      >
      <div v-else class="deck-logo-fallback">logo</div>
    </div>
  </footer>
</template>
