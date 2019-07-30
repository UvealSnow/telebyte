<template>
  <div class="hero-unit">
    <div class="hero-default">
      <div class="hero-mask"></div>
      <div class="hero-polygon"></div>
    </div>

    <div class="nav">
      <slot/>
    </div>

    <div class="hero-content">
      <span>tu aliado estratégico</span>
      <h1>los mejores en telecomunicaciones de la región</h1>
      <a class="btn btn-white btn-rounded" href="#servicios">
        nuestros servicios
      </a>
    </div>
  </div>
</template>

<script type="text/javascript">
  export default {
    //
  }
</script>

<style lang="scss" scoped>
  @import '../assets/style/mixins';
  @import '../assets/style/variables';

  .hero-unit {
    @include full-background;
    width: 100vw;
    height: 540px;
    position: relative;
    background-position: left;
    background-image: url('~@/assets/images/hero-bg.png');
  }

  .hero-default {
    height: 100%;
    width: 100%;
    clip-path: polygon(60% 0, 100% 0, 40% 100%, 00% 100%);

    @media screen and (min-width: 1024px) {
      clip-path: polygon(60% 0, 90% 0, 40% 100%, 10% 100%);
    }
  }

  .hero-mask {
    height: 100%;
    width: 100%;
    top: 0;
    z-index: 1;
    position: absolute;
    background-color: transparentize($primary, .75);
  }

  .nav {
    top: 0;
    width: 100vw;
    position: absolute;
  }

  .hero-polygon {
    @include full-background;
    height: 100%;
    width: 100%;
    z-index: 0;
    top: 0;
    position: absolute;
    background-image: url('~@/assets/images/polygon-bg.png');
  }

  .hero-content {
    top: 60%;
    left: 50%;
    color: white;
    width: 85%;
    max-width: 1022px;
    position: absolute;
    text-align: center;
    text-transform: uppercase;
    transform: translate(-50%, -50%);

    span {
      font-size: 12px;
      font-weight: bold;
      margin-bottom: 32px;
      color: rgba(255, 255, 255, .75);
    }

    h1 {
      color: white;
      margin: 24px 0;
      line-height: 1.2;
      font-size: 25px;
    }

    @media screen and (min-width: 768px) {
      h1 {
        margin-top: 8px;
        font-size: 30px;
      }
    }

    @media screen and (min-width: 1024px) {
      h1 {
        font-size: 50px;
      }
    }
  }
</style>
