<!-- Template goes here -->
<template>

    <div class="navigation-wrapper">

        <ul class="navigation-list">
            
            <li class="navigation-item"><router-link to="/home" exact>Home</router-link></li>
            <li class="navigation-item"><router-link to="/categories" exact>Categories</router-link></li>
            <li class="navigation-item"><router-link to="/random" exact>Random</router-link></li>

        </ul>

    </div>

</template>

<script lang="ts">
    /* Importing */
    import { Component, Vue }  from 'vue-property-decorator'

    /* Components */
    @Component

    /* Classes */
    export default class Header extends Vue {

    }
</script>

<style scoped>

    .navigation-wrapper .navigation-list  {
        list-style: none;
        display: flex;
        justify-content: center;
        padding: 0;
        margin: 0;
    }

    .navigation-wrapper .navigation-list .navigation-item {
        padding: 25px;
    }

    .navigation-wrapper .navigation-list .navigation-item a {
        color: #03396c;
        text-transform: uppercase;
        opacity: 0.7;
    }

    .navigation-wrapper .navigation-list .navigation-item a.router-link-active {
        opacity: 1;
    }

   @media only screen and (max-width:767px){
        .navigation-wrapper .navigation-list .navigation-item {
            padding: 10px;
        }
    }


</style>