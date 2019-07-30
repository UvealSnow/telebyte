<template>
  <div class="collapsables">
    <div class="collapsable-bg">
      <div class="green-mask"></div>
    </div>

    <div class="collapsable-container">
      <div class="titles">
        <span>sobre nosotros</span>
        <h1>puntos clave sobre nosotros</h1>
        <p>Conócenos, aquí puedes encontrar información sobre nuestra empresa.</p>
      </div>

      <CollapsableItem v-for="(collapsable, index) in collapsables" :info="collapsable" :key="index"></CollapsableItem>
    </div>
  </div>
</template>

<script type="text/javascript">
  import CollapsableItem from './parts/CollapsableItem.vue'

  export default {
    data() {
      return {
        collapsables: [
          {
            title: 'Historia',
            text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.'
          },
          {
            title: 'Calidad',
            text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.'
          },
          {
            title: 'Misión y visión',
            text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.'
          }
        ]
      }
    },

    components: {
      CollapsableItem
    }
  }
</script>

<style lang="scss" scoped>
  @import '../assets/style/mixins';
  @import '../assets/style/variables';

  .collapsables {
    margin: auto;
    display: block;
    max-width: 1200px;
    position: relative;
  }

  .collapsable-bg {
    @include full-background;
    top: 0;
    width: 50%;
    height: 520px;
    display: none;
    position: static;
    background-position: left;
    background-image: url('~@/assets/images/hero-bg.png');

    @media screen and (min-width: 768px) {
      display: inline-block;
    }

    .green-mask {
      width: 100%;
      height: 100%;
      background-color: transparentize($primary, .5);
    }
  }

  .collapsable-container {
    width: 100%;
    display: inline-block;
    margin-top: 25px;
    padding: 50px 16px 16px;
    background-color: transparentize(#c4c4c4, .85);

    @media screen and (min-width: 768px) {
      width: 50%;
      float: right;
      height: 460px;
      position: absolute;
      overflow-y:  scroll;
      bottom: 8px;
    }
  }
</style>
