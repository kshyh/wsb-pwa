<template>
    <div>
      <transition name="modal">
        <div v-if="show">
          <div class="overlay" @click.self="$emit('close')">
            <div class="modal">
              <h2 class="modal-header">{{ this.header }}</h2>
              <div class="modal-content">
                <div class="thumbs">
                  <img
                    v-for="image in getImagesWithoutCurrent()"
                    :src="image.image"
                    :key="image.name"
                    @click="onClickThumb(image)"
                  />
                </div>
                <button class="iconButton" v-on:click="previousImage()">
                  <i class="fa-solid fa-chevron-left"></i>
                  previous
                </button>
                <transition name="fade">
                  <div class="image">
                    <h3>{{ this.localCurrentImage.name }}</h3>
                    <img :src="this.localCurrentImage.image" />
                  </div>
                </transition>
                <button class="iconButton" v-on:click="nextImage()">
                  next
                  <i class="fa-solid fa-chevron-right"></i>
                </button>
              </div>
            </div>
          </div>
        </div>
      </transition>
    </div>
  </template>

  <script>
  import "@fortawesome/fontawesome-free/css/all.css";
  import "@fortawesome/fontawesome-free/js/all.js";
  import Image from "~/models/image";

  export default {
    name: "Modal",
    props: {
      show: {
        type: Boolean,
        default: () => false,
      },
      header: {
        type: String,
        default: () => "",
      },
      images: {
        type: [],
        default: () => [],
      },
      currentImage: {
        type: Image,
        default: () => {},
      },
    },
    computed: {
      localCurrentImage: {
        get: function () {
          return this.currentImage;
        },
        set: function (value) {
          this.$emit("update-current-image", value);
        },
      },
    },
    methods: {
      nextImage() {
        let number = this.images.indexOf(this.localCurrentImage);
        if (number < this.images.length - 1) {
          this.localCurrentImage = this.images.at(number + 1);
        } else {
          this.localCurrentImage = this.images.at(0);
        }
      },
      previousImage() {
        let number = this.images.indexOf(this.localCurrentImage);
        if (number > 0) {
          this.localCurrentImage = this.images.at(number - 1);
        } else {
          this.localCurrentImage = this.images.at(this.images.length - 1);
        }
      },
      onClickThumb(image) {
        this.localCurrentImage = image;
      },
      getImagesWithoutCurrent() {
        return this.images.filter((p) => p !== this.localCurrentImage);
      },
    },
  };
  </script>

  <style scoped>
  .thumbs {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: space-around;
    align-content: center;
    gap: 5px 5px;
    margin-right: 0.5rem;
  }

  .thumbs img {
    width: 60px;
    height: 60px;
  }
  .thumbs img:hover {
    border: 1px solid black;
  }

  .iconButton {
    background: none;
    font-size: 2rem;
    border: none;
  }
  </style>
