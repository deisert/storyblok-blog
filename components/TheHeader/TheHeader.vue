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

<style scoped>
    .main-header {
        position: fixed;
        top: 0; 
        left: 0;
        width: 100%;
        background-color: #022d30;  
        height: 4.5rem;
    }

    .main-nav{
        height: 100%;
    }

    .nav-links {
        list-style: none;
        margin: 0;
        padding: 0;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100%;
    }
</style>

