<template>
  <div>
    <v-row>
      <v-col v-for="(image, index) in images" :key="index" cols="3">
        <v-img :src="image.url" aspect-ratio="1"></v-img>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  data () {
    return {
      images: [
        // Здесь вы можете добавить начальные изображения или загружать их из базы данных или сервера
        { url: 'https://example.com/image1.jpg' },
        { url: 'https://example.com/image2.jpg' },
        { url: 'https://example.com/image3.jpg' }
      ]
    }
  }
}
</script>
