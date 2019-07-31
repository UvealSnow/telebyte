<template>
  <div id="galeria" class="container section gallery">
    <div class="titles">
      <span>Galería</span>
      <h1>Trabajos recientes</h1>

      <div class="gallery__container">
        <GalleryItem v-for="edge in $static.projects.edges" :item="edge.node" :key="edge.node.id"/>
      </div>
    </div>
  </div>
</template>

<static-query>
  query Project {
    projects: allProject(sortBy: "date", filter: { published: { eq: true }}) {
      edges {
        node {
          id
          title
          path
          tags
          date(format: "DD/MM/YYYY")
          coverImage(width: 770, height: 380, blur: 10)
        }
      }
    }
  }
</static-query>

<script type="text/javascript">
  import GalleryItem from './parts/GalleryItem.vue'

  export default {
    components: {
      GalleryItem
    }
  }
</script>

<style lang="scss" scoped>
  .gallery__container {
    // background-color: red;
  }
</style>