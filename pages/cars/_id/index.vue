<template>
    <div>
        <TopNav />
        <div>
            {{ $route.params.id }}        
        </div>
    </div>
</template>
<script>
import TopNav from '../../../components/Nav/TopNav.vue'
export default {
  name: 'CarsIdPage',
  components: { TopNav},

  methods: {
    showInfo: () => {
        console.log('Witaj w konsoli')
        alert('Witaj')
    }
  }
}</script>
<style scoped></style>