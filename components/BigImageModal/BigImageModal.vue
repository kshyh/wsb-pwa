<template>
    <div>
      <transition name="modal">
        <div v-if="show">
          <div class="overlay" @click.self="closeModal()">
            <div class="modal">
              <div class="modal-content">
                <img :src="this.imageUrl" />
              </div>
            </div>
          </div>
        </div>
      </transition>
    </div>
  </template>

  <script>
  export default {
    name: "Modal",
    data() {
      return {
          show: false,
          imageUrl: ''
      }
    },
    created() {
      this.$nuxt.$on("showBigImageModal", (url) => {
          this.show = true;
          this.imageUrl = url;
      });
    },
    methods: {
      closeModal(){
          this.show = false;
      }
    },
  };
  </script>

  <style scoped>
  .modal {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    width: auto;
    height: auto;
    max-width: 80vh;
    margin: 0 auto;
    padding: 5px;
    background-color: #fff;
    transition: all 0.2s ease-in;
    font-family: Helvetica, Arial, sans-serif;
  }

  .overlay {
    position: fixed;
    top: 0;
    left: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, .9);
    z-index: 999;
    transition: opacity 0.2s ease;
  }

  .modal-content {
    display: flex;
    flex-direction: row;
  }

  .modal-content img {
    width: 100%;
  }

  </style>
