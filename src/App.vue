<template>
  <div>
    <Posts :posts="posts" @showPost="showPost"/>
    <Content :activePost="activePost"/>
  </div>
</template>

<script>
import Posts from './components/Posts.vue'
import Content from './components/Content.vue'

export default {
  name: 'App',
  components: {
    Posts,
    Content,
  },
  data() {
    return {
      posts: [
        {
          id: 1,
          title: 'first title',
          body: 'loralksdjasjslkdjlskdsjadlkjsdlakjdalksjdlkjsd',
        },
        {
          id: 2,
          title: 'second title',
          body: 'sluzxcxzcxzczcg',
        },
        {
          id: 3,
          title: 'third title',
          body: 'sluhjkhjkhjkhjkhg',
        },
        {
          id: 4,
          title: 'fourth title',
          body: 'sluqweqwewtreyrtrtug',
        },
        {
          id: 5,
          title: 'fifth title',
          body: 'slxcvxcvxcvcxvxug',
        },
        {
          id: 6,
          title: 'fifth title',
          body: 'slu6556555564533653463465g',
        },
        {
          id: 7,
          title: 'fifth title',
          body: 'slufnghjjt765675756756757g',
        },
        {
          id: 8,
          title: 'fifth title',
          body: 'slcxvcxxcvxcvxv67676ug',
        },
        {
          id: 9,
          title: 'fifth title',
          body: 'slug',
        },
        {
          id: 10,
          title: 'fifth title',
          body: 'slug',
        },
      ],
      activePost: Object,
    }
  },
  methods: {
    showPost(post){
      console.log(post);
      this.activePost = post;
    }
  },
}
</script>

<style>
body {
  padding: 0;
  margin: 0;
  width: 100%;
  height: 100%;
}

.posts-list {
  width: 40%;
  height: 95vh;
  padding: 10px;
  border: 3px solid black;
  margin: 10px;
  border-radius: 20px;
  float: left;
}

.link {
  border: 2px solid black;
  width: auto;
  padding: 19px;
  margin: 10px 10px 10px 10px;
  border-radius: 10px;
  cursor: pointer;
}

.links {
  height: 85vh;
}

.post-title {
  text-transform: uppercase;
}

.content {
  border: 3px solid black;
  border-radius: 20px;
  width: 53%;
  height: 95vh;
  float: right;
  padding: 10px;
  margin: 10px;
  font-size: 20px;
}
</style>
