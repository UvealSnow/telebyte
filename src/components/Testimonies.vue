<template>
  <div class="section container testimonies">
    <div class="background"></div>

    <div class="testimony__slider">
      <div class="titles center">
        <span>clientes</span>
        <h1>testimonios</h1>
      </div>

      <div class="slider__controls">
        <ChevronLeftIcon size="3x" @click="$refs.slider.prev()" />
        <ChevronRightIcon size="3x" @click="$refs.slider.next()" />
      </div>

      <siema ref="slider" :current.sync="current_slide" :options="siemaOptions">
        <Testimony v-for="(testimony, index) in testimonies" :item="testimony" :key="index" />
      </siema>
    </div>
  </div>
</template>

<script type="text/javascript">
  import Testimony from './parts/Testimony.vue'
  import { ChevronRightIcon, ChevronLeftIcon } from 'vue-feather-icons'

  export default {
    data() {
      return {
        testimonies: [
          {
            author: {
              name: 'Holly Molly',
              avatar: '../../assets/images/holly-molly.jpg'
            },
            text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.'
          },
          {
            author: {
              name: 'Maryna Gomez',
              avatar: '/assets/images/maryna-gomez.jpg'
            },
            text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.'
          }
        ],
        current_slide: 0,
        siemaOptions: {
          perPage: 1,
          loop: true
        }
      }
    },

    components: {
      Testimony,
      ChevronLeftIcon,
      ChevronRightIcon
    }
  }
</script>

<style lang="scss" scoped>
  @import './../assets/style/mixins';
  @import './../assets/style/variables';

  .section {
    height: 630px;
    position: relative;
    margin-bottom: 50px;
  }

  .testimony__slider {
    box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.25);
  }

  .slider__controls {
    top: 140px;
    width: 280px;
    left: 50%;
    position: absolute;
    transform: translateX(-50%);
    z-index: 9999;

    svg {
      cursor: pointer;
    }

    svg:last-of-type {
      float: right;
    }
  }

  .background {
    @include full-background;
    width: 100%;
    height: 472px;
    position: relative;
    background-image: url('~@/assets/images/bandwidth.jpg');

    &:after {
      content: '';
      width: 100%;
      height: 100%;
      position: absolute;
      background-color: transparentize($primary, .3);
      clip-path: polygon(0 0, 76% 0, 18% 100%, 0% 100%);
    }

    &:before {
      content: '';
      width: 100%;
      height: 100%;
      position: absolute;
      background-color: transparentize(black, .5);
    }
  }

  .testimony__slider {
    width: 90%;
    top: 225px;
    margin: auto;
    position: absolute;
    left: 50%;
    background-color: white;
    padding: 32px;
    transform: translateX(-50%);
  }
</style>