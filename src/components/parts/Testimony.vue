<template>
  <div class="testimony">
    <div class="testimony__author"></div>
    <div class="testimony__text">
      <p v-text="item.text"></p>
      <span v-text="`- ${item.author.name}`"></span>
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
  .testimony__author {
    width: 92px;
    height: 92px;
    background-color: gray;
    margin: 32px auto;
    border-radius: 50%;
  }

  .testimony__text {
    text-align: center;
    width: 70%;
    margin: auto;

    p {
      color: black;
      font-size: .8em;
      line-height: 1.8;
      font-weight: 300;
    }

    span {
      font-weight: bold;
      font-size: .7em;
    }
  }
</style>