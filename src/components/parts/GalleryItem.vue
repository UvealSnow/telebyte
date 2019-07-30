<template>
  <div class="gallery-item" :style="`background-image: url('${item.coverImage.src}')`">
    <div class="item__content">
      <div class="item__text">
        <h5 v-text="item.title"></h5>

        <div class="item__tags">
          <span v-for="tag in item.tags" v-text="tag"></span>
        </div>

        <g-link :to="item.path" class="btn btn-sm btn-white">Ver más</g-link>
      </div>
    </div>
  </div>
</template>

<script type="text/javascript">
  export default {
    props: {
      item: {
        required: true,
        type: Object
      }
    }
  }
</script>

<style lang="scss" scoped>
  @import '../../assets/style/mixins';
  @import '../../assets/style/variables';

  .gallery-item {
    @include full-background;
    width: 100%;
    height: 360px;
    margin-top: 16px;
    display: inline-block;

    .item-mask {
      opacity: 0;
      position: absolute;
      height: 100%;
      width: 100%;
      z-index: 0;
      top: 0;
    }

    &:hover {
      .item-mask {
        opacity: 1
      }
    }

    .item__content {
      opacity: 0;
      width: 100%;
      height: 100%;
      transition: .5s;
      text-align: center;
      position: relative;
      vertical-align: middle;
      background-color: transparentize($primary, .5);

      &:hover {
        opacity: 1
      }
    }

    .item__text {
      top: 50%;
      left: 50%;
      width: 80%;
      position: absolute;
      transform: translate(-50%, -50%);

      h5, span {
        margin: 0;
        color: white;
      }

      h5 {
        font-size: 1.2em;
        text-transform: uppercase;
      }

      span {
        font-size: .7em;
        font-weight: 300;

        &:not(:last-of-type) {
          margin-right: 16px;
        }
      }

      .btn {
        margin-top: 32px;
      }
    }

    .item__tags {
      margin-bottom: 16px;
    }

    @media screen and (min-width: 768px) {
      width: calc(50% - 20px);
      height: 287px;
      margin: 40px 40px 0 0;

      &:nth-child(even) {
        margin-right: 0;
      }
    }

    @media screen and (min-width: 1024px) {
      width: calc(31.9% - 13px);

      &:nth-child(even) {
        margin-right: 40px;
      }

      &:nth-child(3n) {
        margin-right: 0;
      }
    }

    @media screen and (min-width: 1264px) {
      width: 373.3px;
      height: 373.3px;
    }
  }
</style>