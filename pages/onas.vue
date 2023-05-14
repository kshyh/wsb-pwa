<template>
    <div>
        <BigImage image="https://u.cyfrowe.pl/600x0/3/9/01_R6MarkII_Front_BODY[1]_1360893833.jpg" />
        <h1>O nas</h1>
        <h2> strona </h2>
        <button @click="showInfo">Kliknij mnie</button>
    </div>
</template>

<script>
import BigImage from '../components/Gallery/bigImage.vue'
export default {
  name: 'OnasPage',
  components: { BigImage},

  methods: {
    showInfo: () => {
        console.log('Witaj w konsoli')
        alert('Witaj')
    }
  }
}
</script>
<style scoped>

</style>