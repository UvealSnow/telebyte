<template>
  <Layout :show-logo="false">
    <Hero>
      <Navbar></Navbar>
    </Hero>

    <About/>
    <Collapsables/>
    <Gallery/>
    <Testimonies/>
    <Posts/>
    <Contact/>
    <Footer/>
  </Layout>
</template>

<script>
  import Hero from '~/components/Hero.vue'
  import Navbar from '~/components/Navbar.vue'
  import About from '~/components/About.vue'
  import Collapsables from '~/components/Collapsables.vue'
  import Gallery from '~/components/Gallery.vue'
  import Testimonies from '~/components/Testimonies.vue'
  import Posts from '~/components/Posts.vue'
  import Contact from '~/components/Contact.vue'
  import Footer from '~/components/Footer.vue'

export default {
  components: {
    Hero,
    Navbar,
    About,
    Collapsables,
    Gallery,
    Testimonies,
    Posts,
    Contact,
    Footer
  },
  metaInfo: {
    title: 'Hello, world!'
  }
}
</script>
