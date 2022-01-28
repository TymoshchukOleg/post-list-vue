<template>
    <div class="content">
        <div class="post-title"> 
            {{ activePost.title }}
        </div>
        <hr>
        <div class="body">
            {{ activePost.body }}
        </div>
    </div>
</template>

<script>
export default {
    props: {
        activePost: {
            type: Object,
        }
    }
}
</script>

<style>

</style>