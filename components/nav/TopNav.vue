<template>
    <div class="nav">
       <ul class="left-nav">
        <li><NuxtLink to="/">Strona domowa</NuxtLink></li>
        <li><NuxtLink to="/onas">O nas</NuxtLink></li>
        <li><NuxtLink to="/customer">Customer</NuxtLink></li>
        <li><NuxtLink to="/gallery">Galeria</NuxtLink></li>
        <li><NuxtLink to="/cars">Cars</NuxtLink></li>
        <li><NuxtLink to="/nasa">Nasa</NuxtLink></li>
       </ul>
    </div>
</template>

<script>

</script>
<style scoped>
.nav {
    width: 100%;
    display: flex;
    border-bottom: 3px solid rgb(255, 255, 255);
    box-shadow: 0px 3px 3px grey;
    background-color: rgb(110, 110, 110);
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