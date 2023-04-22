<template>
    <div>
      <TopNav />
      <h1>Nasa</h1>
      <div>
        <input v-model="message" placeholder="search..." />
        <button @click="$event => find()">SEARCH</button>
      </div>
      <div style="display: flex; flex-wrap: wrap; width: 100vm; justify-content: center;">
        <img 
          :src="value.links[0].href"
          v-for="(value, index) in dataArr"
          :key="index"
          style="width: 100px; height: 100px; object-fit: cover; padding: 5px;"
         />
      </div>
    </div>
</template>
<script>
import TopNav from '../../components/Nav/TopNav.vue';
import axios from 'axios';

export default {
  name: 'NasaPage',
  components: { TopNav},

  created() {
    this.fetchData('sun')
  },

  data() {
    return {
      dataArr: [],
      message: ''
    }
  },

  methods: {
    find() {
      this.fetchData(this.message)
    },

    async fetchData(value) {
        await axios.get(`https://images-api.nasa.gov/search?q=${value}`)
        .then(res => {
          this.dataArr = res.data.collection.items;
        })
        .catch(error => {
          console.log(error)
        })
    }
  }
}</script>
<style scoped>

</style>