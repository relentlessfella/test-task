<template>
  <div class="container">
    <div class="image-container">
      <img
        v-for="(item, index) in data"
        :key="index"
        :src="item.images"
        @click="openImage(item.images, item.title, item.author)"
        class="gallery-image"
        hover:
      />
    </div>
    <div v-if="selectedImage" class="overlay">
      <div class="modal">
        <button class="close-button" @click="closeImage">X</button>
        <div class="selectedImage">
          <div class="titleAuthor">{{ title }} by {{ author }}</div>
          <img :src="selectedImage" class="modal-image" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import data from './data.json'

export default {
  data() {
    return {
      data,
      selectedImage: null,
      author: null,
      title: null
    }
  },
  methods: {
    openImage(imageSrc, title, author) {
      this.selectedImage = imageSrc
      this.author = author
      this.title = title
    },
    closeImage() {
      this.selectedImage = null
    }
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  max-width: 1800px;
  width: 60%;
}
.pageTitle {
  text-decoration: none;
  color: #fff;
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  text-transform: uppercase;
  font-size: 17px;
  font-weight: 600;
}
.image-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 2fr));
  grid-auto-rows: minmax(300px, auto);
  grid-gap: 15px;
  box-shadow: 0px 0px 5px rgba(0, 0, 0, 0.25);
  padding: 15px;
}
.gallery-image {
  max-width: 100%;
  cursor: pointer;
  background-size: cover;
  background-position: center;
  font-size: 0.8em;
  box-sizing: border-box;
  border-radius: 5px;
}

.overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.7);
  display: flex;
  justify-content: center;
  align-items: center;
}
.selectedImage {
  margin: 0px auto;
}
.modal {
  background: #fff;
  padding: 10px;
  border-radius: 5px;
  position: relative;
  text-align: center;
  width: 800px;
  height: 720px;
}
.modal-image {
  max-width: 85%;
  max-height: 80%;
  border-radius: 5px;
}

.close-button {
  padding: 10px 14px;
  border-radius: 5px;
  border: 1px solid #fff;
  background-color: #bbbbbb;
}

.close-button {
  position: absolute;
  top: 10px;
  right: 10px;
  cursor: pointer;
  color: #000;
}
.titleAuthor{
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  font-weight: 600;
  font-weight: 600;
}
</style>
