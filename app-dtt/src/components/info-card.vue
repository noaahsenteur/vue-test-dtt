<!-- Template goes here -->
<template>

    <router-link :to="'post/' + id" class="info-card">

        <div class="head-content">
            {{ title }}
        </div>

        <div class="publishing-date">
            published year : {{ date }}
        </div>

        <div class="body-content">
            {{ content }}
        </div>

    </router-link>

</template>


<script lang="ts">

/* Import */
import { Vue, Prop, Component } from 'vue-property-decorator'

/* Component */
@Component

/* Classes */
export default class App extends Vue {

  @Prop({ default: 'John doe' }) readonly title!: string
    @Prop({ default: 'John doe' }) readonly content!: string
    @Prop() readonly id!: string
    @Prop() readonly date!: string

}

</script>

<style>

.info-card {
    height: 100%;
    text-align: center;
    border-radius: 5px;
    overflow: hidden;
    box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
    display: flex;
    flex-direction: column;
}

.info-card .head-content{
    padding-bottom: 25px;
    background: #6497b1;
    color: white;
    padding: 25px;
    height: 100px;
    display: flex;
    justify-content: center;
    align-items: center;
}

.info-card .body-content {
    font-size: 0.75em;
    padding: 10px 15px 25px 25px;
}

.publishing-date {
    font-size: 0.65em;
    text-transform: uppercase;
    padding-top: 10px;
    font-weight: 800;
    color: gray;
}

</style>
