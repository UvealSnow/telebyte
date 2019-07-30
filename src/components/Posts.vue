<template>
  <div class="section container posts">
    <div class="titles center">
      <span>blog</span>
      <h1>noticias de la industria</h1>
    </div>

    <div class="post__container section">
      <siema ref="slider" :current.sync="current_slide" :options="siemaOptions">
        <PostCard v-for="edge in $static.posts.edges" :post="edge.node" :key="edge.node.id" />
      </siema>

      <div class="slider__controls">
        <ChevronLeftIcon size="3x" @click="$refs.slider.prev()" />
        <ChevronRightIcon size="3x" @click="$refs.slider.next()" />
      </div>
    </div>
  </div>
</template>

<static-query>
  query Post {
    posts: allPost(sortBy: "date", filter: { published: { eq: true }}) {
      edges {
        node {
          id
          title
          path
          description
          tags {
            id
            title
            path
          }
          author
          date(format: "DD/MM/YYYY")
          coverImage(width: 770, height: 380, blur: 10)
          ...on Post {
            id
            title
            path
          }
        }
      }
    }
  }
</static-query>

<script type="text/javascript">
  import PostCard from './parts/PostCard.vue'
  import { ChevronRightIcon, ChevronLeftIcon } from 'vue-feather-icons'

  export default {
    data() {
      return {
        current_slide: 0,
        siemaOptions: {
          perPage: {
            500: 1,
            1024: 2,
            1440: 3
          },
          loop: true
        }
      }
    },

    components: {
      PostCard,
      ChevronRightIcon,
      ChevronLeftIcon
    }
  }
</script>

<style lang="scss" scoped>
  .slider__controls {
    width: 200px;
    margin: auto;

    svg {
      float: left;
      cursor: pointer;
      vertical-align: top;
      color: rgba(0, 0, 0, .5);

      &:last-of-type {
        float: right;
      }
    }
  }
</style>