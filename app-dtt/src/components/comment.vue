<template>
    <div class="comment">
        <div class="head">
            {{ email }}
        </div>
        <div class="body">
            {{ content }}
        </div>
    </div>
</template>

<script lang="ts">
import { Component, Vue, Prop } from 'vue-property-decorator'
  
@Component
export default class Comment extends Vue {
  @Prop({ default: 'E-mail' }) readonly email: string
  @Prop({ default: 'content' }) readonly content: string
}

</script>

<style>


</style>
