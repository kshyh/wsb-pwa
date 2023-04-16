<template>
    <div class="user">
        <p><span>imie: </span><span>{{ name }}</span></p>
        <p><span>salary: </span><span>{{ salary }}</span></p>
        <p><span>age: </span><span>{{ age }}</span></p>
    </div>
</template>

<script>
export default {
  props: {
    name: {
        type: String,
        default: () => ''
    },
    salary: {
        type: String,
        default: () => ''
    },
    age: {
        type: String,
        default: () => ''
    }
  },
  created() {
    console.log(this.name);
    // vue2 doc, serviceWorkery
  }
}
</script>
<style scoped>
    .user {
        padding: 30px;
    }
    p {
        margin-bottom: 10px;
    }
</style>