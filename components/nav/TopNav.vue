<template>
    <div class="nav">

       <ul class="left-nav">
        <li><NuxtLink to="/">Strona domowa</NuxtLink></li>
        <li><NuxtLink to="/onas">O nas</NuxtLink></li>
       </ul>

    </div>
</template>

<script>

</script>
<style scoped>
.nav {
    width: 100%;
    display: flex;
    border-bottom: 3px solid yellow;
    box-shadow: 0px 3px 3px grey;
    background-color: blue;
}

.left-nav {
    display: flex;
    flex-direction: row;
    list-style: none;
}
.left-nav li {
    padding: 10px 20px;
    color: white;
}
.left-nav li a {
    cursor: pointer;
    color: white;
}

/* px, rem, em, vh, vw, % */
.item {
}
.item2 {
    display: flex;
    flex-direction: column;
}
</style>