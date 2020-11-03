<template>
  <div id="app">
    <header>
      <app-header></app-header>
    </header>
    <div class="container">
      <router-view></router-view>
    </div>
    <footer>
      <app-footer></app-footer>
    </footer>
  </div>
</template>

<script lang="ts">
  import { Component, Vue } from 'vue-property-decorator'
  import Header from '@/components/header.vue'
  import Footer from '@/components/footer.vue'
  
@Component({
  components: {
    'app-header':Header,
    'app-footer': Footer
  }
})
export default class App extends Vue {
  
}

</script>

<style>

  @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@500&display=swap');
  body{
    font-family: 'Montserrat', sans-serif;
    padding: 0px;
    margin: 0px;
  }

  a {
    color: black;
    text-decoration: none;
  }

  p,h1,h2,h3,h4 {
    padding: 0;
    margin: 0;
  }

  #app header {
    margin-bottom: 25px;
    position: fixed;
    width: 100%;
    background: white;
  }

  .center-item {
    display: flex;
    justify-content: center;
  }

  .flex-row {
    
  }

  .container {
    padding-top:100px;
  }

    .content-wrap {
      margin: 0 auto;
  }
    .content-wrap .posts-overview {
      display: flex;
      flex-direction: row;
      flex-wrap: wrap;
    }

    .info-card {
    width: calc(100% / 5);
    display: flex;
    flex-direction: column;

  }


</style>
