<template>
    <div>
      <TopNav/>
      <div class="gallery"></div>
    </div>
</template>

<script>
import TopNav from '../components/Nav/TopNav.vue'
export default {
  name: 'GalleryPage',
  components: { TopNav },

  methods: {
    showInfo: () => {
        console.log('Witaj w konsoli')
        alert('Witaj')
    }
  }
}
</script>
<style scoped>
.nav {
  position: fixed;
  top: 0;
}
  .gallery {
    width: 100vw;
    height: 100vh;
    background-color: lightslategray;
  }
</style>