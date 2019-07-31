<template>
  <div id="contacto" class="container contact">
    <div class="contact__left">
      <div class="titles">
        <h1>Envíanos <span>un mensaje</span></h1>
      </div>

      <form method="POST" action="#">
        <div class="form-control">
          <label>Nombre completo</label>
          <input type="text" name="contact_name" required>
        </div>

        <div class="form-control">
          <label>Email</label>
          <input type="email" name="contact_email" required>
        </div>

        <div class="form-control">
          <label>Tu mensaje</label>
          <textarea name="message" required></textarea>
        </div>

        <button class="btn btn-green">
          Enviar mensaje
        </button>
      </form>
    </div>

    <div class="contact__right">
      <div class="titles">
        <h1>Nuestros <span>datos</span></h1>
      </div>

      <div class="data">
        <div class="datum">
          <div class="icon">
            <MapPinIcon size="2x" />
          </div>
          <div class="text">
            <h5>Dirección</h5>
            <p>Cerrada Vista Hermosa #156. Fracc. Bosques de Linda Vista. Villa de Pozos.</p>
          </div>
        </div>

        <div class="datum">
          <div class="icon">
            <MailIcon size="2x" />
          </div>
          <div class="text">
            <h5>Correo electrónico</h5>
            <p>hola@telebyte.mx</p>
          </div>
        </div>

        <div class="datum">
          <div class="icon">
            <PhoneIcon size="2x" />
          </div>
          <div class="text">
            <h5>Número telefónico</h5>
            <p>+52 (444) 198 2929</p>
          </div>
        </div>

        <div class="datum">
          <div class="icon">
            <WatchIcon size="2x" />
          </div>
          <div class="text">
            <h5>Horario</h5>
            <p>Lun ~ Vié de 8am a 6pm</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script type="text/javascript">
  import { MapPinIcon, MailIcon, PhoneIcon, WatchIcon } from 'vue-feather-icons'

  export default {
    data() {
      return {
        //
      }
    },

    components: {
      MapPinIcon, MailIcon, PhoneIcon, WatchIcon
    }
  }
</script>

<style lang="scss" scoped>
@import './../assets/style/variables';

  .contact {
    margin: 200px auto;
    border-radius: 3px;
    background-color: white;
    box-shadow: 0px 6px 14px rgba(0, 0, 0, 0.25);

    form {
      margin-top: 45px;

      .btn-green {
        font-size: 1em;
        box-shadow: none;
        margin-top: 32px;
        color: white !important;
        background-color: $primary !important;

        &:hover {
          background-color: darken($primary, 10%) !important;
        }
      }
    }

    .form-control {
      label {
        font-size: .8em;
        font-weight: bold;
        display: block;
        margin: 8px 0;
      }

      input, textarea {
        padding: 16px;
        font-size: 1em;
        width: 100%;
        height: 50px;
        outline: none;
        display: block;
        border-radius: 5px;
        font-family: 'Rubik';
        border: 1px solid rgba(0, 0, 0, .3);
      }

      textarea {
        min-height: 150px;
      }
    }
  }

  .contact__left {
    padding: 60px 40px;
  }

  .contact__right {
    padding: 60px 40px;
    border-top: 1px solid rgba(0, 0, 0, .2);
  }

  .data {
    margin-top: 32px;
  }

  .datum {
    .icon {
      margin-right: 32px;
      position: relative;
      vertical-align: top;
      margin-top: 16px;
      color: $primary;
      display: inline-block;
    }

    .text {
      display: inline-block;

      @media screen and (min-width: 768px) {
        width: calc(100% - 122px);
      }

      h5 {
        margin-top: 16px;
        text-transform: uppercase;
      }
    }
  }

  @media screen and (min-width: 1024px) {
    .contact__right,
    .contact__left {
      vertical-align: top;
      display: inline-block;
    }

    .contact__left {
      width: calc(100% - 482px);
    }

    .contact__right {
      width: 482px;
      height: 100%;

      border-left: 1px solid rgba(0, 0, 0, .2);
    }
  }
</style>