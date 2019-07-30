<template>
  <div class="container">
    <div class="navbar">
      <div class="navbar__transparent">
        <div class="logo">
          <g-image src="~/assets/images/telebyte-white.png"></g-image>
        </div>

        <div class="hamburger">
          <MenuIcon size="2x"/>
        </div>

        <div class="actions">
          <a href="#">
            <div class="action">
              <div class="action__icon">
                <PhoneIncomingIcon/>
              </div>
              <div class="action__text">
                <h5>Llámanos</h5>
                <p>+52 (444) 198 2929</p>
              </div>
            </div>
          </a>

          <a href="#">
            <div class="action">
              <div class="action__icon">
                <MailIcon/>
              </div>
              <div class="action__text">
                <h5>Envíanos un correo</h5>
                <p>hola@telebyte.mx</p>
              </div>
            </div>
          </a>

          <a href="#">
            <div class="action">
              <div class="action__icon">
                <WatchIcon/>
              </div>
              <div class="action__text">
                <h5>Horario de atención</h5>
                <p>Lun-Vie 8:00am ~ 6:00pm</p>
              </div>
            </div>
          </a>
        </div>
      </div>

      <div class="navbar__white">
        <div class="links">
          <a to="/">Inicio</a>
          <a to="#servicios">Servicios</a>
          <a to="#galeria">Galería</a>
          <a to="#testimonios">Testimonios</a>
          <a to="#contacto">Contáctanos</a>
        </div>

        <div class="icons">
          <a class="icon" href="#">
            <FacebookIcon/>
          </a>
          <a class="icon" href="#">
            <TwitterIcon/>
          </a>
          <a class="icon" href="#">
            <LinkedinIcon/>
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script type="text/javascript">
  import { MenuIcon, FacebookIcon, TwitterIcon, LinkedinIcon, PhoneIncomingIcon, MailIcon, WatchIcon } from 'vue-feather-icons'

  export default {
    data() {
      return {
        is_open: false
      }
    },

    methods: {
      toggleNavbar() {
        this.is_open = !this.is_open
      }
    },

    components: {
      MenuIcon,
      MailIcon,
      WatchIcon,
      TwitterIcon,
      FacebookIcon,
      LinkedinIcon,
      PhoneIncomingIcon
    }
  }
</script>

<style lang="scss" scoped>
  @import '../assets/style/variables';

  .navbar {
    position: relative !important;
    z-index: 99;
    height: 173px;
    padding-top: 31px;
    text-align: center;

    .navbar__transparent {
      width: 100%;
      padding: 0 16px;

      .hamburger {
        color: white;
        float: right;
        margin-top: 10px;
        display: none;

        @media screen and (max-width: 959px) {
          display: inline-block;
        }
      }

      .actions {
        float: right;
        display: none;

        @media screen and (min-width: 960px) {
          display: inline-block;
        }

        a:not(:last-of-type) {
          margin-right: 32px;
          display: inline-block;
        }
      }

      .action {
        display: inline-block;

        .action__icon, .action__text {
          display: inherit;
        }

        .action__icon {
          margin-right: 8px;
        }

        .action__text {
          //
        }

        h5, p {
          margin: 0;
          color: white;
          text-align: left;
        }

        h5 {
          font-size: .7em;
        }

        p {
          font-size: .5em;
        }

        svg {
          color: $primary;
        }
      }
    }

    .navbar__white {
      width: 100%;
      height: 61px;
      display: none;
      margin-top: 30px;
      border-radius: 3px;
      background-color: white;

      @media screen and (min-width: 768px) {
        display: inline-block;
      }

      &:after {
        content: " ";
        visibility: hidden;
        display: block;
        height: 0;
        clear: both;
      }

      .links {
        float: left;
        padding: 21px 32px;
        display: inline-block;

        a {
          float: left;
          color: black;
          font-size: 14px;
          cursor: pointer;
          text-align: left;
          text-align: left;
          font-weight: bold;
          transition: .35s;
          text-transform: uppercase;

          &:hover {
            color: $primary;
          }

          &:not(:last-of-type) {
            margin-right: 34px;
          }
        }
      }

      .icons {
        float: right;
        display: none;

        @media screen and (min-width: 960px) {
          display: inline-block;
        }

        .icon {
          height: 61px;
          transition: .35s;
          display: inline-block;
          border-left: 1px solid rgba(0, 0, 0, .15);

          &:hover {
            svg {
              color: $primary;
            }
          }

          svg {
            margin: 19px 25px;
            color: rgba(0, 0, 0, .35);
          }
        }
      }
    }
  }

  .logo {
    float: left;
    max-width: 178px;
    display: inline-block;
  }
</style>