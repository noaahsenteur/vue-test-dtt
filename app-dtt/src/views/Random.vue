<template>
    <div>
        <div class="toolbar">
            <button v-on:click="Randomize">Randomize</button>
        </div>
        <div class="content-wrap center-item">
            <info-card :title="post.title" :content="post.body" :id="post.id.toString()" ></info-card>
        </div>
    </div>
</template>

<script lang="ts">
    import { Vue, Component } from 'vue-property-decorator' 
    import Card from '../components/info-card.vue';
    import Axios from 'axios'
    
    @Component({
        components: {
            'info-card': Card
        }
    })
    export default class Random extends Vue {
        
        post: object = {}

        RandomInt(min: number, max: number): number {
            min = Math.ceil(min);
            max = Math.floor(max);
            return Math.floor(Math.random() * (max - min) + min);
        }

       Randomize(): void {
             Axios.get('https://jsonplaceholder.typicode.com/posts/'+ this.RandomInt(0,100)).then(response => {
                this.post = response.data;
          })
       } 

        created(){
            this.Randomize();
        }


    }
</script>

<style scoped>

    .toolbar {
        display: flex;
        justify-content: center;
    }
    .toolbar button {
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

    .toolbar button:hover {
        opacity: 1;
    }



</style>