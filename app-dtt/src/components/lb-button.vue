<template>
    <button>{{ text }}</button>
</template>


<script lang="ts">
    import { Vue, Component, Prop } from 'vue-property-decorator' 

    @Component
    export default class Home extends Vue { 
        @Prop({ default: 'John doe' }) readonly text: string

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

    button:hover {
        opacity: 1;
    }
</style>