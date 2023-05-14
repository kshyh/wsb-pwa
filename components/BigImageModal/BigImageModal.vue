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
    width: 500px;
    height: 500px;
    margin: 0px auto;
    padding: 20px;
    background-color: #fff;
    border-radius: 2px;
    box-shadow: 0 2px 8px 3px;
    transition: all 0.2s ease-in;
    font-family: Helvetica, Arial, sans-serif;
  }
  
  .modal-content {
    display: flex;
    flex-direction: row;
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
    background: #00000094;
    z-index: 999;
    transition: opacity 0.2s ease;
  }
  img {
      width: 400px;
  }
  </style>
  