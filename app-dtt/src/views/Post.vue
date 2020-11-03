<template>
    <div class="content-wrap">
        <div class="post-wrap center-item">
            <div class="post-detail">
            <div class="head-content">
                <h1>
                    {{ post.title }}
                </h1>
            </div>
            <div class="body-content">
                <p>
                    {{ post.body }}
                </p>
                </div>
            </div>
        </div>
        <div class="post-comments">
            <div class="title">
                <h3> Gerelateerde comments </h3>
                <post-comments v-for="(comment, index) in comments" :email="comment.email" :content="comment.body" :key="index"></post-comments>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
import { Vue, Component } from 'vue-property-decorator'
import Axios from 'axios'
import Comments from '../components/comment.vue'

@Component({
    components:{
        'post-comments' : Comments
    }
})
export default class Post extends Vue {
    id: string = this.$route.params.id
    post: object = {}
    comments: object = {}


     created(){
          Axios.get('https://jsonplaceholder.typicode.com/posts/' + this.id ).then(response => {
              this.post = response.data;        
          })

          Axios.get('https://jsonplaceholder.typicode.com/posts/' + this.id + '/comments').then(response => {
              this.comments = response.data;
              console.log(response.data);
          }); 

      }

}
</script>

<style scoped>
    .content-wrap .post-detail {
        width: 50%;
        border-radius: 5px;
        overflow: hidden;
        text-align: center;
        box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
    }

    .content-wrap .post-detail .head-content {
        padding: 25px;
        color: white;
        background:#6497b1;
    }

    .content-wrap .post-detail .body-content {
        padding: 25px;
    }

    .content-wrap .post-wrap {
        margin-bottom: 25px;
    }

</style>