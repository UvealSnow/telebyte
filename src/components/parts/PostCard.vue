<template>
  <div class="post-card">
    <div class="post">
      <div class="post__thumbnail" :style="`background-image: url('${post.coverImage.src}')`"></div>
      <div class="post__body">
        <div class="post__metadata">
          <span>por <a href="#">{{ post.author }}</a></span>
          <span v-text="post.date"></span>
        </div>
        <div class="post__text">
          <h1 v-text="post.title"></h1>
          <p v-text="post.description"></p>
        </div>
      </div>
      <div class="post__footer">
        <!-- {{ post.tags }} -->
        <g-link v-for="tag in post.tags" :to="tag.path">
          {{ tag.title }}
        </g-link>
      </div>
    </div>
  </div>
</template>

<script type="text/javascript">
  export default {
    props: {
      post: {
        required: true,
        type: Object
      }
    },

    data() {
      return {
        //
      }
    }
  }
</script>

<style lang="scss" scoped>
  @import '../../assets/style/mixins';

  .post-card {
    padding: 0 20px;
    margin-bottom: 20px;
  }

  .post__thumbnail {
    @include full-background;
    width: 100%;
    height: 260px;
  }

  .post {
    box-shadow: 0px 6px 14px rgba(0, 0, 0, 0.25);
  }

  .post__body {
    padding: 40px 40px 0;
  }

  .post__metadata {
    span {
      font-size: .5em;
      font-weight: 300;
      vertical-align: middle;
      color: rgba(0, 0, 0, .7);

      a {
        font-weight: bold;
        color: rgba(0, 0, 0, .7);
      }
    }

    span:last-of-type {
      float: right;
      margin-top: 7px;
    }
  }

  .post__text {
    h1, p {
      color: rgba(0, 0, 0, .7);
    }

    h1 {
      font-size: 1.5em;
      line-height: 43px;
    }

    p {
      font-size: .8em;
    }
  }

  .post__footer {
    width: 70%;
    padding: 16px 40px;
    position: relative;
    border-top: 1px solid rgba(0, 0, 0, .2);

    a {
      margin: 8px 0;
      font-size: .5em;
      font-weight: bold;
      vertical-align: middle;
      color: rgba(0, 0, 0, .5);
      text-transform: uppercase;

      &:not(:last-of-type) {
        margin-right: 16px;
      }
    }

    &:before {
      content: '';
      width: 80%;
      height: 10px;

      background-color: red;
    }
  }
</style>