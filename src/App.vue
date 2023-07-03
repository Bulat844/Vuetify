<template>
  <v-app>
    <v-container>
      <h1>Моя фотогалерея</h1>
      <ImageUploader />
      <ImageGallery />
    </v-container>
  </v-app>
</template>

<script>
import ImageUploader from './components/ImageUploader.vue'
import ImageGallery from './components/ImageGallery.vue'

export default {
  components: {
    ImageUploader,
    ImageGallery
  }
}
</script>
