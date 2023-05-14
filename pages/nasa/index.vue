<template>
    <div>
      <div class="container">
        <h1>Nasa - {{ currentCollection }}</h1>
        <div class="search">
          <input v-model="message" placeholder="search..." />
          <button @click="$event => find()">SEARCH</button>
        </div>
        <div style="display: flex; flex-wrap: wrap; width: 100vm; justify-content: center;">
          <template v-for="(value) in dataArr">
            <template v-for="(link, index) in value.links">
              <img
                v-if="index === 0"
                :data-index="index"
                :src="link.href"
                style="width: 100px; height: 100px; object-fit: cover; padding: 5px;"
               />
            </template>
          </template>
          <!-- <img 
            v-for="(value, index) in dataArr"
            :src="value.links[0].href"
            :key="index"
            style="width: 100px; height: 100px; object-fit: cover; padding: 5px;"
           /> -->
        </div>
      </div>
    </div>
</template>
<script>
import axios from 'axios';

export default {
  name: 'index',

  created() {
    this.fetchData('sun')
  },

  data() {
    return {
      dataArr: [],
      message: '',
      currentCollection: '',
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
          this.currentCollection = value;
          this.message = "";
        })
        .catch(error => {
          console.log(error)
        })
    }
  }
}</script>
<style scoped>
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
h1 {
  margin-top: 20px;
  margin-bottom: 20px;
}
.search {
  margin-bottom: 20px;
}
</style>