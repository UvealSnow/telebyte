<template>
  <div class="icon-card">
    <div class="icon">
      <component :is="card.icon" size="3x"></component>
      <h1 v-text="card.title"></h1>
      <p v-text="card.text"></p>
    </div>
  </div>
</template>

<script type="text/javascript">
  export default {
    props: {
      card: {
        required: true,
        type: Object
      }
    }
  }
</script>

<style lang="scss" scoped>
  @import '../../assets/style/variables';

  svg {
    color: $primary;
    display: block;
    margin-bottom: 16px;
  }

  h1 {
    font-size: 1.3em;
    line-height: 1.5;
    color: rgba(0, 0, 0, 1);
    text-transform: uppercase;
  }

  p {
    font-size: 1.2em;
    line-height: 1.5;
    color: rgba(0, 0, 0, .5);
  }

  @media screen and (min-width: 1024px) {
    .icon-card {
      width: 220px;
      margin-left: 20px;
      vertical-align: top;
      display: inline-block;
    }

    h1 {
      font-size: .8em;
    }

    p {
      font-size: .65em;
    }
  }

  @media screen and (min-width: 1264px) {
    .icon-card {
      width: 260px;
    }
  }
</style>