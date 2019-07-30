<template>
  <Layout>
    <div class="post-title">
      <h1 class="post-title__text">
        <p>This is a project</p>
        <p v-text="$page.project.title"></p>
      </h1>
    </div>
  </Layout>
</template>

<page-query>
  query Project ($path: String!) {
    project: project (path: $path) {
      title
    }
  }
</page-query>

<script type="text/javascript">
  export default {
    mixins: [],

    props: {
      //
    },

    data() {
      return {
        //
      }
    },

    methods: {
      //
    },

    created() {
      //
    },

    mounted() {
      //
    }
  }
</script>