<!-- Template goes here -->
<template>

    <div class="comment">

        <div class="head">

            <div class="email">
                {{ email }}
            </div>

            <div class="date">
                {{ date }}
            </div>

        </div>
        
        <div class="body">
            <div class="content">
                {{ content }}
            </div>
        </div>

    </div>

</template>

<script lang="ts">
/* Importing */
import { Component, Vue, Prop } from 'vue-property-decorator'
  
/* Components */
@Component

/* Classes */
export default class Comment extends Vue {

    /* Props */  
    @Prop({ default: 'E-mail' }) readonly email!: string
    @Prop({ default: 'content' }) readonly content!: string
    @Prop({ default: 'content' }) readonly date!: string
}

</script>

<style scoped>

    .comment {
        background: rgb(230 230 230);
        font-size: 0.9em;
        border-radius: 5px;
        box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
        padding: 15px;
        margin-bottom: 15px;
    }

    .comment .head {
        padding-bottom: 10px;
        font-weight: 700;
        display: flex;
        justify-content:space-between;
    }

    .comment .head .date {
        font-weight: 600;
        font-size: 0.75em;
    }

    @media only screen and (max-width:767px){
         .comment .head {
             flex-direction: column;
         }
    }

</style>
