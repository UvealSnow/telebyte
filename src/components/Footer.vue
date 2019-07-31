<template>
  <div class="footer-container">
    <div class="footer"></div>
    <div class="content container">
      <div class="content__left">
        <g-image class="logo" src="~/assets/images/telebyte-white.png"></g-image>
        <p>Duis semper mauris vitae purus rhoncus suscipit. Nunc dictum dapibus tellus, at viverra risus pharetra id. Nulla facilisi. Ut mollis et augue non gravida.</p>
        <a href="#"><FacebookIcon /></a>
        <a href="#"><TwitterIcon /></a>
        <a href="#"><LinkedinIcon /></a>
      </div>

      <div class="content__right">
        <h5>CONTÁCTANOS</h5>

        <div class="data">
          <div class="datum">
            <div class="icon">
              <MapPinIcon />
            </div>

            <p>Cerrada Vista Hermosa #156. Fracc. Bosques de Linda Vista. Villa de Pozos. San Luis Potosí, S.L.P.</p>
          </div>

          <div class="datum">
            <div class="icon">
              <MailIcon />
            </div>

            <p>hola@telebyte.mx</p>
          </div>

          <div class="datum">
            <div class="icon">
              <PhoneIncomingIcon />
            </div>

            <p>+52 (444) 198 2929</p>
          </div>

          <div class="datum">
            <div class="icon">
              <WatchIcon />
            </div>

            <p>LUN - VIE 8:00 am ~ 5:00 pm</p>
          </div>

        </div>
      </div>
    </div>
    <div class="thanks">
      <p>Hecho por <a href="https://www.kevinavila.pro">@UvealSnow</a></p>
      <p>© Telebyte 2019</p>
    </div>
  </div>
</template>

<script type="text/javascript">
  import { FacebookIcon, TwitterIcon, LinkedinIcon, PhoneIncomingIcon, MailIcon, WatchIcon, MapPinIcon } from 'vue-feather-icons'

  export default {
    components: {
      MailIcon,
      WatchIcon,
      MapPinIcon,
      TwitterIcon,
      FacebookIcon,
      LinkedinIcon,
      PhoneIncomingIcon
    }
  }
</script>

<style lang="scss" scoped>
  @import './../assets/style/mixins';
  @import './../assets/style/variables';

  .footer-container {
    // z-index: -9;
    min-height: 780px;
    margin-top: -500px;
    position: relative;
  }

  .footer {
    @include full-background;
    width: 100vw;
    z-index: -1;
    height: 1050px;
    position: relative;
    background-image: url('~@/assets/images/fiber.jpg');

    &:before {
      content: '';
      width: 100vw;
      height: 100%;
      position: absolute;
      background-color: rgba(0, 0, 0, .5);
    }

    @media screen and (min-width: 1024px) {
      height: 850px;
    }
  }

  .content {
    left: 50%;
    top: 400px;
    min-height: 200px;
    height: auto;
    position: absolute;
    transform: translateX(-50%);

    .content__left {
      p {
        color: white;
        font-size: 1em;
        margin: 32px 0;
        line-height: 1.8;
        background-color: transparent;
      }

      a {
        color: white;

        &:not(:last-of-type) {
          margin-right: 32px;
        }
      }
    }

    .content__right {
      color: white;

      h5 {
        margin-top: 0;
        color: white;
      }

      .datum {
        .icon, p {
          vertical-align: top;
          display: inline-block;
        }

        .icon {
          margin: 5px 20px 0 0;
        }

        p {
          width: calc(100% - 50px);
        }
      }
    }

    @media screen and (min-width: 1024px) {
      .content__left,
      .content__right {
        display: inline-block;
        vertical-align: top;
      }

      .content__left {
        width: 360px;
      }

      .content__right {
        margin-left: 40px;
        width: calc(100% - 400px);
      }

      .datum p {
        max-width: 550px;
        font-size: .8em;
      }
    }

    @media screen and (min-width: 1268px) {
      .content__right {
        margin-left: 80px;
        width: calc(100% - 440px);
      }
    }
  }

  .logo {
    max-width: 178px;
  }

  .thanks {
    padding: 32px 16px;
    width: 100vw;
    background-color: black;

    p, a {
      margin: 0;
      color: white;
      font-size: 14px;
    }
  }
</style>