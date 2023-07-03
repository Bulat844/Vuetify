<template>
  <div>
    <!-- Кнопка для выбора изображения -->
    <input type="file" @change="handleImageChange" accept="image/*">
    <!-- Отображение загруженного изображения (предварительный просмотр) -->
    <div v-if="imageUrl">
      <img :src="imageUrl" alt="Uploaded Image" style="max-width: 300px;">
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      imageUrl: null // Ссылка на загруженное изображение
    }
  },
  methods: {
    handleImageChange (event) {
      // При выборе файла, проверяем, что файл был выбран
      if (event.target.files && event.target.files.length > 0) {
        const file = event.target.files[0]
        this.readImage(file)
      }
    },
    readImage (file) {
      // Используем объект FileReader для чтения изображения в формате Data URL
      const reader = new FileReader()

      // Обработчик события, вызывающийся при успешном чтении файла
      reader.onload = (event) => {
        this.imageUrl = event.target.result // Сохраняем Data URL изображения
      }

      // Обработчик события, вызывающийся при ошибке чтения файла
      reader.onerror = (event) => {
        console.error('Error reading the file:', event.target.error)
      }

      // Читаем файл в формате Data URL
      reader.readAsDataURL(file)
    }
  }
}
</script>
