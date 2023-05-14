<template>
    <div>
        <div>
            {{ $route.params.id }}        
        </div>
    </div>
</template>
<script>
export default {
  name: 'CarsIdPage',

  methods: {
    showInfo: () => {
        console.log('Witaj w konsoli')
        alert('Witaj')
    }
  }
}</script>
<style scoped></style>