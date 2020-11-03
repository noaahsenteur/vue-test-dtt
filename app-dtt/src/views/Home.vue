<template>
    <div class="content-wrap">
        <div class="toolbar center-item">
        <button v-if="desc" v-on:click="SortDesc">Sorteer van laag naar hoog</button>
        <button v-else-if="!desc" v-on:click="SortAsc">Sorteer van hoog naar laag</button>
        </div>
        <div class="posts-overview center-item">
            <app-card v-for="(item,index) in homeitems.slice(0,10)" v-bind:key="index" :title="item.title" :content="item.body" :id="item.id.toString()" :date="item.date"></app-card>
        </div>
    </div>
</template>

<script lang="ts">
    import { Vue, Component } from 'vue-property-decorator' 
    import Axios from 'axios'
    import Card from '@/components/info-card.vue'
    import Button from '@/components/lb-button.vue'

    @Component({
        components: {
            'app-card': Card,
            'light-button': Button,
        }
    })


    export default class Home extends Vue {

    public homeitems: Array<object> = []
        
    desc = true;

    created(){

          Axios.get('https://jsonplaceholder.typicode.com/posts').then(response => {
                const tempArray: Array<object> = [];
                for(const key in response.data){
                    const date = new Date();
                    const year = date.getFullYear() - Math.floor(Math.random() * 10);
                    response.data[key].date = year;
                    tempArray.push(response.data[key]);
                }
                this.homeitems = tempArray;
          });
      }

    SortDesc(){
        this.homeitems.sort((a: any, b: any): any =>{
                this.desc = false;
                if(a.date > b.date){
                    return 1;
                } else {
                    return -1;
                }
            })
        }

      SortAsc(){
        this.homeitems.sort((a: any, b: any): any =>{
                this.desc = true;
                if(a.date < b.date){
                    return 1;
                } else {
                    return -1;
                }
            })
        }
    }
</script>

<style scoped>
button {
        opacity: 0.8;
        background: #6497b1;
        border: none;
        padding: 10px 25px;
        text-transform: uppercase;
        font-size: 0.75em;
        border-radius: 25px;
        color: white;
        letter-spacing: 1px;
        outline: none;
        -webkit-box-shadow: 0px 0px 2px 0px rgba(50, 50, 50, 1);
        -moz-box-shadow: 0px 0px 2px 0px rgba(50, 50, 50, 1);
        box-shadow: 0px 0px 2px 0px rgba(50, 50, 50, 1);
    }

</style>