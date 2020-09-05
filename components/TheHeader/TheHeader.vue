<!-- Its called THE Header because, thats officially Vue Syntax for components u only use once apparently.-->
<template>
    <header class ="main-header">
        <nav class ="main-nav">
            <ul class="nav-links">
                <li><nuxt-link to="/">All Posts</nuxt-link></li>
                <li><nuxt-link to="/about">About</nuxt-link></li>
            </ul>
        </nav>
    </header>
</template>


<script>
export default {

}
</script>

<style scoped>
    .main-header {
        position: fixed;
        top: 0; 
        left: 0;
        width: 100%;
        background-color: #022d30;  
    }
</style>

