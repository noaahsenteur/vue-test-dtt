<template>
    <div class="footer-wrap">
        <div class="links-wrapper">
            <router-link to="/sitemap"> Sitemap </router-link>
            -
            <a href="https://www.linkedin.com/in/noah-senteur-04a9b5153/"> Linked in </a>
            -
            <a href="https://wa.me/31623947567"> Whatsapp </a>
        </div>
        <div class="credits">
            Noah Senteur
        </div>
    </div>
</template>

<script lang="ts">
 import { Component, Vue } from 'vue-property-decorator'

@Component
export default class Footer extends Vue {

}
</script>

<style scoped>

    .footer-wrap {
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    .footer-wrap .links-wrapper {
        font-weight: 500;
        text-transform: uppercase;
        padding: 5px;
        color: white;
        border-bottom: 0.5px solid rgba(0,0,0,0.1);
    }

    .footer-wrap .links-wrapper a {
        color: white;
    }

    .footer-wrap .credits {   
        padding-top: 10px;
        text-transform: uppercase;
        font-size: 0.75em;
    }

    @media only screen and (max-width:767px){
        .footer-wrap .links-wrapper {
            font-size: 0.75em;
        }
    }

</style>