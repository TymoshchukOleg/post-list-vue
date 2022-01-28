<template>
    <div class="posts-list">
        <div class="links">
            <div class="link" 
            v-for="post in paginatedPosts" 
            :key="post.id" 
            @click="showPost(post)
            ">
            <div class="post-title"> 
                {{ post.title }}
            </div>
        </div>
        </div>
        <div class="pagination">
            <button @click="prevPage" :disabled="pageNumber==0">Previous</button>
            <button @click="nextPage" :disabled="pageNumber >= pageCount-1">Next</button>
        </div>
    </div>
</template>

<script>
export default {
    data() {
      return {
        pageNumber: 0,
        size: 9,
      }  
    },
    emits: ["showPost"],
    props: {
        posts: {
            type: Array,
            default: () => [],
        },
    },
    methods: {
        showPost: function (post) {
            this.$emit('showPost', post);
        },
        nextPage(){
            this.pageNumber++;
            console.log(this.pageNumber);
        },
        prevPage(){
            this.pageNumber--;
            console.log(this.pageNumber);
        },
    },
    computed: {
        paginatedPosts: function () {
            const start = this.pageNumber * this.size,
            end = start + this.size;
            return this.posts.slice(start, end);
        },
        pageCount: function () {
            let length = this.posts.length,
            size = this.size;

            return Math.ceil(length/size);
        }
    }
}
</script>

<style>
    .pagination {
        margin: auto;
        width: 38%;
        margin-top: 16px;
    }
    .pagination button {
        padding: 10px;
        width: 100px;
        margin: 5px;
    }
</style>