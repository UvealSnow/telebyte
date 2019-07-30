<template>
  <div class="collapsable">
    <div class="collapsable__header" @click="toggleState">
      <component :is="is_open ? 'ChevronUpIcon' : 'ChevronDownIcon'"></component>
      <h5 v-text="info.title"></h5>
    </div>
    <div :class="`collapsable__body ${is_open ? 'active' : ''}`">
      <p v-text="info.text"></p>
    </div>
  </div>
</template>

<script type="text/javascript">
  import { ChevronDownIcon, ChevronUpIcon } from 'vue-feather-icons'
  export default {
    data() {
      return {
        is_open: false
      }
    },

    methods: {
      toggleState() {
        this.is_open = !this.is_open
      }
    },

    props: {
      info: {
        type: Object,
        required: true
      }
    },

    components: {
      ChevronUpIcon,
      ChevronDownIcon
    }
  }
</script>

<style lang="scss" scoped>
  .collapsable__header {
    padding: 16px 0 10px;
    position: relative;
    cursor: pointer;
    border-top: 2px solid rgba(0, 0, 0, .15);
    // border-bottom: 1px solid rgba(0, 0, 0, .15);

    svg, h5 {
      display: inline-block;
      color: rgba(0, 0, 0, .5);
    }

    h5 {
      margin: 0 16px;
      position: relative;
      top: -6px;
      font-weight: normal;
    }
  }

  .collapsable__body {
    display: none;

    &.active {
      display: block;
    }
  }
</style>