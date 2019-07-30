<template>
  <div id="sobre-nosotros" class="section container about-us">
    <div class="pseudo-card">
      <div class="titles">
        <span>sobre nosotros</span>
        <h1>telebyte</h1>
        <p>Con más de 30 años de experiencia, Telebyte S.A. de C.V. ofrece el mejor servicio disponible en la región.</p>
        <g-link to="/sobre-nosotros">Leer más</g-link>
      </div>
    </div>

    <IconCard v-for="(card, index) in cards" :card="card" :key="index"/>
  </div>
</template>

<script type="text/javascript">
  import IconCard from '~/components/parts/IconCard.vue'
  import Collapsables from './Collapsables.vue'
  import { WifiIcon, LockIcon, TrendingUpIcon } from 'vue-feather-icons'

  export default {
    data() {
      return {
        cards: [
          {
            icon: WifiIcon,
            title: 'diseño de redes lan y wan',
            text: 'Con más de 30 años de experiencia, Telebyte S.A. de C.V. ofrece el mejor servicio disponible en la región.'
          },
          {
            icon: LockIcon,
            title: 'seguridad física e informática',
            text: 'Con más de 30 años de experiencia, Telebyte S.A. de C.V. ofrece el mejor servicio disponible en la región.'
          },
          {
            icon: TrendingUpIcon,
            title: 'Diseño de proyectos',
            text: 'Con más de 30 años de experiencia, Telebyte S.A. de C.V. ofrece el mejor servicio disponible en la región.'
          }
        ]
      }
    },

    components: {
      IconCard,
      WifiIcon,
      LockIcon,
      TrendingUpIcon,
      Collapsables
    }
  }
</script>

<style lang="scss" scoped>
  @import '../assets/style/variables';

  .pseudo-card {
    margin-bottom: 32px;
  }

  @media screen and (min-width: 1024px) {
    .pseudo-card {
      display: inline-block;
      width: 240px;
    }
  }

  @media screen and (min-width: 1264px) {
    .pseudo-card {
      width: 300px;
    }
  }
</style>