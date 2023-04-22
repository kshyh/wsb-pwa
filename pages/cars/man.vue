<template>
    <div>
        <TopNav />
    </div>
</template>
<script>
import TopNav from '../../components/Nav/TopNav.vue'
export default {
  name: 'ManPage',
  components: { TopNav},

  methods: {
    showInfo: () => {
        console.log('Witaj w konsoli')
        alert('Witaj')
    }
  }
}</script>
<style scoped></style>