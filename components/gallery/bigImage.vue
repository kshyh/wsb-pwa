<template>
    <div class="img-container">
        <img :src="image" class="img" />
    </div>
</template>
<script>
export default {
  name: 'BigImage',
  props: {
    image: {
        type: String,
        default: () => 'Pusty string'
    }
  }
}
</script>
<style scoped>

.img-container {
    text-align: center;
}
.img {
    width: 50%;
    height: auto;
    margin: 20px auto;
}
</style>